<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>天气卡片</title>
    <style>
        .f img{
            width:500px;height: 500px;
         position: absolute;left: 1100px;top: 20px;
        opacity:0.5;
        filter:alpha(opacity=40);
        border-radius:35px;
        }
        #bone img:hover{
        opacity:0.1;
        }
        footer {
    padding: 20px;text-align: center;background: transparent;margin-top: 20px;
    color:black;font-size: 100%;
    position:absolute;left: 500px;top:830px;
    }

        .e img{
            display: block;
            width:300px;height:400px;
            position: fixed;left:1200px;top:50px;
            z-index: 100;
        }
        table,td,th
        {
            border:1px solid black;
            left: 650px;top:100px;
        }
        table{
            width:100%;
        }
        th{
            height:50px;
        }
        .box2{
  color:violet;
  font-size: 300%;
  margin-top: 0.5em;
  font-family: STXinwei;/*华文新魏*/
  width:500px;height:400px;background-color: transparent;position: absolute;left: 250px;top:100px;
}

        
        #overflowText{
    background: transparent;
    color:black;
    padding: 15px;
    width: 80%;
    height: 200px;
    overflow: scroll;
    border: 1px;
}
.color{
    font-size: 50px;
    color: rgb(156, 143, 188);

}
.a{
    font-size: 25px;
    color: paleturquoise;
    
}
.a:hover{
    background-color:plum;
}
.b{
    color: salmon;
    font-size: 25px;
}
.c{
    font-size: 20px;
    color: white;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
p{
    background-color: transparent;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-style: inherit;
    color: white;
}
p.padding{
    padding: 25px 50px;
}
        img{
            float: right;
}
.box1{
    display:block;
    width: 400px;
    height: 400px;
    padding: 20px;
    border-width: 25px;
    border-color: transparent
    
    ;
    border-style: solid;
    font-size: 200%;
    margin: 10px;
    background-color: transparent;
    padding-left: 100;

}
body
{
    background:url(../previewFix.jpg);
}
    </style>
</head>
<body>
    <a href="https://map.baidu.com/search/%E6%9D%AD%E5%B7%9E%E5%B8%82/@13382475,3514398,12z?querytype=s&wd=%E6%9D%AD%E5%B7%9E%E5%B8%82&c=179&provider=pc-aladin&pn=0&device_ratio=2&da_src=shareurl" target='_blank' h1 class="color"><strong><em>杭州天气-钱塘区</em></strong></a>
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <div class="e">
        <img src="../88888.png">
    </div>
    <div class="f">
        <img src="000.jpg">
    </div>
    <div class="box1"> 
        <div class="b"><steong>城市:</steong>
    <a href="https://baike.baidu.com/item/%E6%9D%AD%E5%B7%9E/147639?fromtitle=%E6%9D%AD%E5%B7%9E%E5%B8%82&fromid=200167&fr=aladdin" target='_blank' span id='nb' class="a"></a><br />
        </div>
        <div class="b"><steong>天气状况:</steong>
    <span id='np' class="a"></a><br />
        </div>
        <div class="b"><steong>温度（℃）:</steong>
    <span id='nx' class="a"></span><br />
        </div>
        <span class="b"><steong>湿度（%rh）:</steong>
    <a href="https://baike.baidu.com/item/%E6%B9%BF%E5%BA%A6/5194459?fr=aladdin" target='_blank' span id='ni' class="a"></a></span><br />
        <div class="b"><steong>风向:</steong>
    <a href="http://www.cma.gov.cn/2011xzt/kpbd/gale/2018050902/201807/t20180717_473666.html" target='_blank' span id='no' class="a"></a><br />
        </div>
        <div class="b"><steong>时间:</steong>
    <a href="http://www.24timemap.com/" target='_blank' span id='nu' class="a"></a><br />
        </div>
    <span id='nn' class="a"></span>
    </div>
    <div class="box2">
        <img src="1.png" alt="">
    </div>
    <button type="button" onclick="myFunction()">每日小问</button>
    <p id="demo1"></p>
    <p id="demo2"></p>
    <p id="demo3"></p>
    <div id="overflowText">
    <p class="c">紫外线强 日出5：54 日落17：42</p>
    <p class="c">今日温度：23-34℃ 风级：3-4级</p>
    <p class="padding">“三级风，属于蒲福风级表中第四个风级，风速为3.4~5.4m/s，12~19km/h。<br /> 风力等级是根据平地上离地10米处风速值大小制定的，在一般情况下以0至12级共13个级别表示，<br />但在特殊情况下存在13级以上的风力等级。<br />3级风称为微风，特征是树叶及小枝摇动不息，旗子展开，高的草摇动不息。”</p>
    <a href="http://zj.weather.com.cn/" p>天气预报</a>
    <table>
        <tr>
            <th>10.7</th>
            <th>10.8</th>
            <th>10.9</th>
        </tr>
        <tr>
            <td>晴天（少云）</td>
            <td>小雨</td>
            <td>小雨</td>
        </tr>
        <tr>
            <td>22℃-30℃</td>
            <td>23℃-29℃</td>
            <td>22℃-30℃</td>
        </tr>
        <tr>
            <td>东北偏东风4级</td>
            <td>东北偏东风4级</td>
            <td>东北偏东风4级</td>
        </tr>
        <tr>
            <td>天气较热建议穿的凉快一点</td>
            <td>天气较热建议穿的凉快一点，带伞</td>
            <td>天气较热建议穿的凉快一点，带伞</td>
        </tr>
    </table>
    <footer>
        <strong>&至此感谢所有提供过帮助的人，希望以后可以多多像学长学姐学习~</strong>
    </footer>
    </div>
    <script>
        prompt('请输入您的名字')
        alert('学长/学姐，hi，萌新制作小卡片，个别做的不好的地方请包含，也期待您提出的建议。谢谢 ')
       
       
            axios({
            url:'https://restapi.amap.com/v3/weather/weatherInfo?key=8192144146e323623ed77ef90c091ed9&city=330100',
            
            method:'get'
        }).then(res=>{
            console.log(res);
            div=document.getElementById('nb');
            div.innerText=res.data.lives[0].city;
            div=document.getElementById('np');
            div.innerText=res.data.lives[0].weather;
            div=document.getElementById('nx');
            div.innerText=res.data.lives[0].temperature;
            div=document.getElementById('ni');
            div.innerText=res.data.lives[0].humidity;
            div=document.getElementById('no');
            div.innerText=res.data.lives[0].winddirection;
            div=document.getElementById('nu');
            div.innerText=res.data.lives[0].windpower;
            div=document.getElementById('nu');
            div.innerText=res.data.lives[0].reporttime;
            
            

        })
       
 
  
        function myFunction(){
            document.getElementById("demo1").innerHTML="今天心情好吗";
            document.getElementById("demo2").innerHTML="今天有没有自己的计划";
            document.getElementById("demo3").innerHTML="助手娘祝你有美好的一天";
        }
    </script>


</body>
</html>