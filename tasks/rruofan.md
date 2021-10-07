<!DOCTYPE html>
<!-- 我想进前端 -->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script type="text/javascript" src="https://webapi.amap.com/maps?v=1.4.15&key=3d3a41e39b9e8e596411f9a48a023c05"></script>
    <script type="text/javascript" src="https://cdn.highcharts.com.cn/highcharts/highcharts.js"></script>
    <style>
        #box01{
    display: table-cell;
    vertical-align: middle;
    width: 100%;
    height: 150px;
    position: absolute;
    top: 50px;
    left: 50%;
    transform: translate(-50%,-50%);
}
#biaoti{
    margin: 0 auto;
    width: 200px;
    height: 70px;
    position: absolute;
    top: 60%;
    left: 50%;
    transform: translate(-50%,-50%);
    text-align: center;
}
#box02{
    display: table-cell;
    vertical-align: middle;
    width:190px;
    height: 30px;
    position: absolute;
    top: 125px;
    left: 50%;
    transform: translate(-50%,0);
}
#box03{
    overflow: hidden;
    display: table-cell;
    vertical-align: middle;
    width: 80%;
    height: 500px;
    position: absolute;
    top: 180px;
    left: 50%;
    transform: translate(-50%,0);
    display: inline;
    border-radius: 5px;
}
#tianqi{
    overflow: hidden;
    margin: 0 auto;
    width: 27%;
    height: 80%;
    position: absolute;
    top: 10%;
    left: 5%;
    border-radius: 10px;
}
#yubao{
    overflow: hidden;
    margin: 0 auto;
    width: 27%;
    height: 80%;
    position: absolute;
    top: 10%;
    left: 20%;
    right: 20%;
    border-radius: 10px;
}
#tu{
    overflow: hidden;
    margin: 0 auto;
    width: 27%;
    height: 80%;
    position: absolute;
    top: 10%;
    right: 5%;
    border-radius: 10px;
}
html {
    background:url(bg.jpg) no-repeat;
    object-fit: cover;
}
#gan{
    overflow: hidden;
    border:1px solid;
    border-radius:20px;
    background-color: steelblue;
    color: whitesmoke;
    border-color: steelblue;
    font-weight: 900;
    width: 50px;
    position: relative;
    vertical-align: center;
    font-size: 18px;
    float:right;
}
#gan:active{
    top: 1px; 
}
#gan:hover{
    border:1px solid;
    border-radius:20px;
    background-color: rgba(13, 99, 156, 0.74);
    color: whitesmoke;
    border-color: rgba(13, 99, 156, 0.74);
    font-weight: 900;
    width: 50px;
    position: relative; 
    vertical-align: center;
    font-size: 18px;
}
#biaoti{
    text-align:center;
    color: white;
    top: 50%;
    bottom: 50%;
    font-family: 微软雅黑;
    font-weight: 700;
    font-size: 50px;
    position: absolute;
    line-height: 0px;
}
#cityname{
    overflow: hidden;
    font-size: 18px;
    font-family: 微软雅黑;
    font-weight: 800;
    color: rgba(13, 99, 156, 0.74);
    position: absolute;
    width: 120px;
    text-align: center;
}
#tianqi{
    font-size: 18px;
    line-height: 20px;
    text-align: center;
    color: snow;
}
#yubao{
    font-size: 18px;
    line-height: 26px;
    text-align: center;
    color: snow;
}

    </style>
</head>
<body>
    <div id="box01">
        <div id="biaoti">
            <p id="bt">天气预报</p>
        </div>
    </div>
    <div id="box02">
        <input type="text" id="cityname" placeholder="请输入城市名">
        <input type="button" name="gan" onclick="search(),getCol('rgba(36, 153, 199, 0.603)')" value="查询" id="gan">
    </div>
    <div id="box03">
        <div id="tianqi">
        <p id="city"></p>
        <p id="weather"></p>
        <p id="temperature"></p>
        <p id="humidity"></p>
        <p id="windDirection"></p>
        <p id="windPower"></p>
        <p id="reportTime"></p>
        <p id="clothes"></p>
        <p id="outdoors" style="word-break:break-all;word-wrap:break-word;"></p>
        </div>
        <div id="yubao">
        <p id="mingtian"></p>
        <p id="mingtian01"></p>
        <p id="houtian"></p>
        <p id="houtian01"></p>
        <p id="dahoutian"></p>
        <p id="dahoutian01"></p>
        <p id="dadahoutian"></p>
        <p id="dadahoutian01"></p>
        </div>
        <div id="tu">
            <div id="container"></div>
        </div>
    </div>
    <script type="text/javascript">
        function getCol(cole) {
				document.getElementById("tianqi").style.background = cole;
                document.getElementById("yubao").style.background = cole;
			}
        function search(){
            AMap.service('AMap.PlaceSearch', function() { //没有constructor，一个是引入key 一个是要有这个的声明
            var placeSearch = new AMap.PlaceSearch(); //用PlaceSearch获取所查询城市的信息，我们主要要从中获取经纬度，用于下面把视窗的中心定位到所查询城市
            placeSearch.search(document.getElementById('cityname').value, function(status, result) { //函数获取带有坐标的对象 查询成功时，result即对应匹配的信息
            // console.log(result)
             AMap.plugin('AMap.Weather', function() {//AMap.ToolBar是地图上的工具控件 AMap.plugin是异步加载插件
            var weather = new AMap.Weather();//AMap.Weather 天气预报插件 查询实时天气信息, 查询的城市到行政级别的城市
            weather.getLive(document.getElementById('cityname').value, function(err, data) {//weather.getLive查询实时天气  function(err, data) err是错误信息 data是返回信息 可以看成一个数组
            if (!err) {
                console.log(data)
                document.getElementById("city").innerHTML='城市/区：' + data.city;
                document.getElementById("weather").innerHTML='天气：' + data.weather;
                document.getElementById("temperature").innerHTML='温度：' + data.temperature + '℃';
                document.getElementById("humidity").innerHTML='空气湿度：' + data.humidity;
                document.getElementById("windDirection").innerHTML='风向：' + data.windDirection;
                document.getElementById("windPower").innerHTML='风力：' + data.windPower;
                document.getElementById("reportTime").innerHTML='发布时间：' + data.reportTime;
                if(data.temperature >= 25){
                    document.getElementById("clothes").innerHTML='穿衣建议：夏装' ;
                }
                if(data.temperature <= 25 && data.temperature >= 15){
                    document.getElementById("clothes").innerHTML='穿衣建议：春秋装' ;
                }
                if(data.temperature <= 15){
                    document.getElementById("clothes").innerHTML='穿衣建议：冬装' ;
                }
                var str = data.weather;
                if(str.indexOf("雨") != -1 ){
                    document.getElementById("outdoors").innerHTML='出行建议：今天可能会下雨\n记得带伞' ;//?
                }
                if(str.indexOf("晴") != -1 ){
                    document.getElementById("outdoors").innerHTML='出行建议：今天天气不错\n注意防晒哟' ;
                }
                if(str.indexOf("云") != -1 ){
                    document.getElementById("outdoors").innerHTML='出行建议：今天还挺适合出行的' ;
                }
                if(str.indexOf("雪") != -1 ){
                    document.getElementById("outdoors").innerHTML='出行建议：今天外面会下雪哟' ;
                }
            }
        });
    });
            AMap.plugin('AMap.Weather', function() {//AMap.ToolBar是地图上的工具控件 AMap.plugin是异步加载插件
            var weather = new AMap.Weather();//AMap.Weather 天气预报插件
            weather.getForecast(document.getElementById('cityname').value, function(err, data0) {// 查询未来4天天气预报
            if (!err) {
                // console.log(data0.forecasts)
                document.getElementById("mingtian").innerHTML=data0.forecasts[0].date + ' ' + data0.forecasts[0].dayWeather + ' ' + data0.forecasts[0].nightTemp + '~' + data0.forecasts[0].dayTemp + '℃';
                document.getElementById("mingtian01").innerHTML='风向：' + data0.forecasts[0].dayWindDir + '  ' + '风力：' + data0.forecasts[0].dayWindPower
                document.getElementById("houtian").innerHTML=data0.forecasts[1].date + ' ' + data0.forecasts[1].dayWeather + ' ' + data0.forecasts[1].nightTemp + '~' + data0.forecasts[1].dayTemp + '℃';
                document.getElementById("houtian01").innerHTML='风向：' + data0.forecasts[1].dayWindDir + '  ' + '风力：' + data0.forecasts[1].dayWindPower
                document.getElementById("dahoutian").innerHTML=data0.forecasts[2].date + ' ' + data0.forecasts[2].dayWeather + ' ' + data0.forecasts[2].nightTemp + '~' + data0.forecasts[2].dayTemp + '℃';
                document.getElementById("dahoutian01").innerHTML='风向：' + data0.forecasts[2].dayWindDir + '  ' + '风力：' + data0.forecasts[2].dayWindPower
                document.getElementById("dadahoutian").innerHTML=data0.forecasts[3].date + ' ' + data0.forecasts[3].dayWeather + ' ' + data0.forecasts[3].nightTemp + '~' + data0.forecasts[3].dayTemp + '℃';
                document.getElementById("dadahoutian01").innerHTML='风向：' + data0.forecasts[3].dayWindDir + '  ' + '风力：' + data0.forecasts[3].dayWindPower
                var chart = Highcharts.chart('container', {
	chart: {
		type: 'line'
	},
	title: {
		text: '未来四天气温预测'
	},
	xAxis: {
		categories: [data0.forecasts[0].date, data0.forecasts[1].date, data0.forecasts[2].date, data0.forecasts[3].date]
	},
	yAxis: {
		title: {
			text: '气温 (°C)'
		}
	},
	plotOptions: {
		line: {
			dataLabels: {
				// 开启数据标签
				enabled: true          
			},
			// 关闭鼠标跟踪，对应的提示框、点击事件会失效
			enableMouseTracking: false
		}
	},
	series: [{
		name: '白天气温',
		data: [data0.forecasts[0].dayTemp, data0.forecasts[1].dayTemp, data0.forecasts[2].dayTemp, data0.forecasts[3].dayTemp]
	}, {
		name: '夜晚气温',
		data: [data0.forecasts[0].nightTemp, data0.forecasts[1].nightTemp, data0.forecasts[2].nightTemp, data0.forecasts[3].nightTemp]
	}]
});
            }
        });
    });
})})}
</script>
</body>
</html>

