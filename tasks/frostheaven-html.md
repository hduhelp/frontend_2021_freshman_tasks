<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <title>天气卡片</title>
</head>
<body>
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <div  id='most'>
        <h1 id='sin'>
            <a href="http://data.cma.cn/" target='_blank'>天气实况</a>
            <div id='spe'><img src='阴.jpg'></div>
        </h1>
        <div class='tag'><em>城市</em>&nbsp&nbsp&nbsp&nbsp&nbsp
            <a href="https://baike.baidu.com/item/%E6%9D%AD%E5%B7%9E/147639?fromtitle=%E6%9D%AD%E5%B7%9E%E5%B8%82&fromid=200167&fr=aladdin" target='_blank'>
                <span id='city'></span>
            </a>
        </div>
        <div class='tag'><em>时间</em>&nbsp&nbsp&nbsp&nbsp&nbsp
            <a href="https://cn.bing.com/search?q=%e5%8c%97%e4%ba%ac%e6%97%b6%e9%97%b4&qs=HS&pq=%e5%8c%97%e4%ba%ac&sc=8-2&cvid=69E6A04B43F748BDA0DB739D3C5B581F&FORM=QBRE&sp=1" target='_blank'>
                <span id='time'></span>
            </a>
        </div>
        <div class='tag'><em>天气</em>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
            <span id='weather'></span>
        </div>
        <div class='tag'><em>温度</em>&nbsp&nbsp&nbsp&nbsp&nbsp
            <span id='temperature'></span>
        </div>
        <div class='tag'><em>风向</em>&nbsp&nbsp&nbsp&nbsp&nbsp
            <a href="https://baike.baidu.com/item/%E9%A3%8E%E5%90%91/4869036?fr=aladdin" target='_blank'>
                <span id='wind'></span>
            </a>
        </div>
        <div class='tag'><em>风力</em>&nbsp&nbsp&nbsp&nbsp&nbsp
            <a href="https://baike.baidu.com/item/%E9%A3%8E%E5%8A%9B%E7%AD%89%E7%BA%A7/8477486?fr=aladdin" target='_blank'>
                <span id='windpower'></span>
            </a>
        </div>
        <div  id='map'>
            <span id='mapword'>悬停于此以显示地图，点击以进入</span>
            <a href="https://cn.bing.com/maps?q=%E6%9D%AD%E5%B7%9E%E7%94%B5%E5%AD%90%E7%A7%91%E6%8A%80%E5%A4%A7%E5%AD%A6&form=ANNNB1&refig=10c92f394e8b42fbbdd4be13abb3b6da" target='_blank'>
                <img src='map.png'>
            </a>
        </div>
        <div class='demo'></div>
        <script>
            alert('萌新制作，学长学姐勿喷~     王宇昂10月');
            axios({
                url:'https://restapi.amap.com/v3/weather/weatherInfo?city=330100&extensions=base&key=38d3b9b3b52a62a427f70ce70f6e5b91',
                method:'get'
            }).then(res=>{
                console.log(res);
                span=document.getElementById('city');
                span.innerText=res.data.lives[0].city;
                span=document.getElementById('time');
                span.innerText=res.data.lives[0].reporttime;
                span=document.getElementById('weather');
                span.innerText=res.data.lives[0].weather;
                span=document.getElementById('temperature');
                span.innerText=res.data.lives[0].temperature;
                span=document.getElementById('wind');
                span.innerText=res.data.lives[0].winddirection;
                span=document.getElementById('windpower');
                span.innerText=res.data.lives[0].windpower;
            }).catch(err=>{
                console.log(err);
            })
        </script>
    </div>
    <div class='box'>
        <strong>“亿”点小建议:</strong>
        <ul>
            <li>昼夜温差需注意，小心着凉来不及</li>
            <li>根据温度勤换衣，自知冷暖最适宜</li>
            <li>天气动态时记心，未雨绸缪有条理</li>
        </ul>
        <div id='bone'><a href='awsl.jpg' target='_blank'><img src='bone.png'></a></div> 
    </div>
    <div>
        <h2><a href="https://tianqi.qq.com/index.htm" target='_blank'>未来预报</a></h2>
        <div>
            <div id='day1' class='case'>
                <span id='fir'><strong>明天</strong></span>
                <span id='dayweather1'></span>
                <span id='nightweather1'></span>
            </div>
            <div id='day2' class='case'>
                <span id='sec'><strong>后天</strong></span>
                <span id='dayweather2'></span>
                <span id='nightweather2'></span>
            </div>
            <div id='day3' class='case'>
                <span id='thi'><strong>大后天</strong></span>
                <span id='dayweather3'></span>
                <span id='nightweather3'></span>
            </div>
            <div id='day'><strong>白天</strong></div>
            <div id='night'><strong>夜晚</strong></div>
        </div> 
        <script>
            axios({
                url:'https://restapi.amap.com/v3/weather/weatherInfo?city=330100&extensions=all&key=38d3b9b3b52a62a427f70ce70f6e5b91',
                method:'get'
            }).then(res=>{
                console.log(res);
                span=document.getElementById('dayweather1');
                span.innerText=res.data.forecasts[0].casts[1].dayweather;
                span=document.getElementById('nightweather1');
                span.innerText=res.data.forecasts[0].casts[1].nightweather;
                span=document.getElementById('dayweather2');
                span.innerText=res.data.forecasts[0].casts[2].dayweather;
                span=document.getElementById('nightweather2');
                span.innerText=res.data.forecasts[0].casts[2].nightweather;
                span=document.getElementById('dayweather3');
                span.innerText=res.data.forecasts[0].casts[3].dayweather;
                span=document.getElementById('nightweather3');
                span.innerText=res.data.forecasts[0].casts[3].nightweather;
            }).catch(err=>{
                console.log(err);
            })
        </script> 
        <div id='a1'><img src='bone2.png'></div> 
        <div id='a2'><img src='bone2.png'></div> 
        <div id='b1'><img src='bone2.png'></div> 
        <div id='b2'><img src='bone2.png'></div> 
        <div id='c1'><img src='bone2.png'></div> 
        <div id='c2'><img src='bone2.png'></div>  
    </div> 
    <footer>
        <strong>&copy116寝室联盟 未经授权，不得转载 开个玩笑，哈哈哈~</strong>
    </footer>
</body>
</html>