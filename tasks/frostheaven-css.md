h1 {  
  font-family: STHupo;/*华文琥珀*/
  letter-spacing: 1px;
  text-transform: uppercase;
  border: 2px solid rgba(42, 247, 110, 0.993);
  background: rgb(161, 189, 189);
  color: yellow;
  box-shadow: 1px 1px 2px rgba(44, 238, 60, 0.932);
  border-radius: 10px;
  padding: 3px 10px;
  display: inline-block;
  cursor: pointer;
  font-size:300%;
  text-shadow: 4px 4px 5px rgb(88, 35, 231);
}
/*主要信息*/
#city{
  color:white;
  font-size:125%;
  width: 300px;
  height:40px;
  background-color:transparent;
  text-decoration:none;
  line-height: 40px;
}
#city:hover{
  background-color:skyblue;
}
#time{
  color:white;
  font-size: 100%;
  width: 1000px;
  height:40px;
  background-color:transparent;
  text-decoration:none;
  line-height: 40px;
  white-space:nowrap;
}
#time:hover{
  background-color:skyblue;
}
#weather {
  color: white;
  font-weight: bold;
  font-size:125%;
  width: 300px;
  height:40px;
  background-color:transparent;
  text-decoration:none;
  line-height: 40px;
}
#weather:hover{
  background-color:skyblue;
}
#temperature{
  color: white;
  font-weight: bold;
  font-size:125%;
  width: 300px;
  height:40px;
  background-color:transparent;
  text-decoration:none;
  line-height: 40px;
}
#temperature:hover{
  background-color:skyblue;
}
#wind{
  color:white;
  font-size:125%;
  width: 300px;
  height:40px;
  background-color:transparent;
  text-decoration:none;
  line-height: 40px;
}
#wind:hover{
  background-color:skyblue;
}
#windpower{
  color:white;
  font-size:125%;
  width: 300px;
  height:40px;
  background-color:transparent;
  text-decoration:none;
  line-height: 40px;
}
#windpower:hover{
  background-color:skyblue;
}
/*信息栏*/
#box{
  width:1000px;height:400px;background-color: transparent;position: absolute;left:1000px;
}
.tag{
  display: block;
  background-color: transparent;
  font-size: 200%;
  color:red;
  width:500px;
  height:50px;
  font-weight: bolder;
}
/*背景图片*/
.demo{
  position:fixed;
  top: 0;
  left: 0;
  width:100%;
  height:100%;
  min-width: 1000px;
  z-index:-10;
  zoom: 1;
  background-color: #fff;
  background: url(bg.png);
  background-repeat: no-repeat;
  background-size: cover;
  -webkit-background-size: cover;
  -o-background-size: cover;
  background-position: center 0;
}
/*天气图片的使用*/
#sin{
  width:300px;height:100px;text-align: center;line-height: 100px;
}
#spe{
  width:150px;height:50px;display: inline-block;position: absolute;left: 320px;
}
img{
  background-color: transparent;width:100px;height: 100px;
}
#most{
  width:1000px;height: 400px;background-color: transparent;
}
/*建议栏*/
.box{
  color:violet;
  font-size: 300%;
  margin-top: 0.5em;
  font-family: STXinwei;/*华文新魏*/
  width:500px;height:400px;background-color: transparent;position: absolute;left: 750px;top:100px;
}
ul{
  line-height: 1.5em;
}
li{
  font-size:50%;color:greenyellow;
}
/*版权copyright*/
footer {
  padding: 20px;text-align: center;background: transparent;margin-top: 20px;
  color:black;font-size: 100%;
  position:absolute;left: 500px;top:700px;
}
/*建议栏骨架图*/
#bone img{
  width:500px;height: 350px;
  position: absolute;left: 0px;top: -20px;
  opacity:0.25;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#bone img:hover{
  opacity:0.1;
}
/*地图存放*/
#map{
  position: absolute;left:0px;top:600px;
  width:13em;
}
#map img{
  width:200px;height:200px;
  opacity:0;
  border-radius: 25px;
  position: absolute;left: 0px;top: -70px;
}
#map img:hover{
  opacity: 1.0;
}
#mapword{
  font-size: 20px;
  color:rgb(184, 177, 177);
  text-align: center;
}
/*未来信息*/
.case{
  display: block;width: 166px;height: 200px;background-color: transparent;
}
h2{
  font-size: 350%;color: turquoise;
  font-family:STXingkai;font-weight: 500%;
  display: block;width: 498px;height: 250px;background-color: transparent;
  position: absolute;left: 770px;top: 430px;
}
#fir{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:800px;top:550px;
  line-height: 20px;font-size: 200%;color:blue;font-family: FZShuTi;
}
#dayweather1{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:800px;top:600px;
  line-height: 20px;
  font-size: 180%;color: white;font-family:STXingkai;
}
#nightweather1{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:800px;top:650px;
  font-size: 180%;color: black;font-family:STXingkai;
}
#sec{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:970px;top:550px;
  line-height: 20px;font-size: 200%;color:blue;font-family: FZShuTi;
}
#dayweather2{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:970px;top:600px;
  font-size: 180%;color: black;font-family:STXingkai;
}
#nightweather2{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:970px;top:650px;
  font-size: 180%;color: black;font-family:STXingkai;
}
#thi{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left: 1140px;top:550px;
  line-height: 20px;font-size: 200%;color:blue;font-family: FZShuTi;
}
#dayweather3{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left: 1140px;top:600px;
  font-size: 180%;color: black;font-family:STXingkai;
}
#nightweather3{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:1140px;top:650px;
  font-size: 180%;color: black;font-family:STXingkai;
}
#day{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:700px;top:600px;
  line-height: 20px;font-size: 200%;color:blue;font-family: FZShuTi;
}
#night{
  display: block;width: 166px;height: 100px;background-color: transparent;
  position:absolute;left:700px;top:650px;
  line-height: 20px;font-size: 200%;color:blue;font-family: FZShuTi;
}
#a1 img{
  width:100px;height: 45px;
  position: absolute;left:775px;top: 590px;
  opacity:0.1;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#a1 img:hover{
  opacity:0.5;
}
#a2 img{
  width:100px;height: 45px;
  position: absolute;left:775px;top: 640px;
  opacity:0.1;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#a2 img:hover{
  opacity:0.5;
}
#b1 img{
  width:100px;height: 45px;
  position: absolute;left:945px;top: 590px;
  opacity:0.1;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#b1 img:hover{
  opacity:0.5;
}
#b2 img{
  width:100px;height: 45px;
  position: absolute;left:945px;top: 640px;
  opacity:0.1;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#b2 img:hover{
  opacity:0.5;
}
#c1 img{
  width:100px;height: 45px;
  position: absolute;left:1115px;top: 590px;
  opacity:0.1;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#c1 img:hover{
  opacity:0.5;
}
#c2 img{
  width:100px;height: 45px;
  position: absolute;left:1115px;top: 640px;
  opacity:0.1;
  filter:alpha(opacity=40);
  border-radius:35px;
}
#c2 img:hover{
  opacity:0.5;
}
/*超链接去下划线*/
a{
  text-decoration: none;
  color:currentColor;
}
a:active{
  color:whitesmoke;
}
