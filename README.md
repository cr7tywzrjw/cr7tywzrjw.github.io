# Welcome to my academic homepage. Hope you have a good day.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Biographical Notes</title>
    <style>
        /*div{*/
        /*    border:1px solid red;*/
        /*}*/
        .info>p{
            margin: 0;
            /*border: 1px solid black;*/
            width: 250px;
            display: inline-block;
            padding: 10px;
            text-indent: 20px;
            /*letter-spacing: 2px;*/
        }
        .container{
            border:1px solid skyblue;
            width: 800px;
            height: 1500px;
            background-color: #eeeeff;
            margin: auto;
        }
        .baseinfo{
            height: 16%;
        }
        .info{
            width: 600px;
            float: left;
        }
        .photo{
            /*border: 1px solid blue;*/
            width: 150px;
            height: 204px;
            float: left;
            padding: 10px;
            margin: 10px 14px auto 6px;
        }
        .education{
            height: 12%;
        }
        .experience{
            height: 34%;
        }
        .skills{
            height: 15%;
        }
        .me{
            height: 15%;
        }
        .line{
            width:760px;
            height: 40px;
            background-color:cadetblue;
            color: white;
            letter-spacing: 2px;
            text-indent: 10px;
            line-height: 40px;
            font-size: 20px;
            margin:10px 18px 0 18px;
        }
        .linetitle{
            color: cadetblue;
            font-size: 16px;
            margin-left: 20px;
        }
        .linetitle span{
            display: inline-block;
            width:30%;
            text-align: center;
        }
        .linetitle span:first-child
        {
           text-align: left;
        }
        .linetitle span:last-child{
            text-align: right;
        }
        .text{
            text-indent: 30px;
 
        }
        .text:before{
            content: "·";
            margin-right: 8px;
            font-size: 20px;
            font-weight: bolder;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="baseinfo">
            <div class="info">
                <p style="font-size: 30px;color: lightseagreen;font-weight: bold">鞠婧祎</p><br>
                <p>政治面貌：XXXX</p> <p>求职意向：XXXX</p><br>
                <p>生日：199X.XX.XX</p> <p>手机：158*******7</p><br>
                <p>民族：汉族</p> <p>邮箱：XXXXXX@qq.com</p><br>
                <p>身高：***cm</p> <p>体重：**kg</p>
 
            </div>
            <div class="photo">
                <img src="./image/attr.jpeg" style="width: 100%;height: 100%;">
            </div>
 
        </div>
 
        <div class="education">
            <div class="line">教育经历/Education</div>
            <div>
                <p class="linetitle"><span>20XX.09-20XX.06</span>  <span>XX大学</span>  <span>XX专业/本科</span></p>
                <p class="text">课程</p>
                <p class="text">课程</p>
            </div>
        </div>
 
        <div class="experience">
            <div class="line">工作经历/Experience</div>
            <div>
                <p class="linetitle"><span>20XX.05-20XX.03</span>   <span>XX公司</span>  <span>XX工程师</span></p>
                <p class="text">负责</p>
                <p class="text">负责</p>
                <p class="text">负责</p>
                <p class="text">负责</p>
                <p class="text">负责</p>
            </div>
 
            <div>
                <p class="linetitle"><span>20XX.04-今</span>  <span>XX公司</span>   <span>XX岗位</span></p>
                <p class="text">负责</p>
                <p class="text">负责</p>
                <p class="text">负责</p>
                <p class="text">负责</p>
            </div>
        </div>
 
        <div class="skills">
            <div class="line">个人技能/Personal Skills</div>
 
            <div>
                <p class="text">技能</p>
                <p class="text">技能</p>
                <p class="text">技能</p>
                <p class="text">技能</p>
            </div>
        </div>
 
        <div class="me">
            <div class="line">自我评价/About Me</div>
 
            <div>
                <p class="text">本人</p>
                <p class="text">本人</p>
                <p class="text">本人</p>
                <p class="text">本人</p>
            </div>
        </div>
 
    </div>
</body>
</html>
