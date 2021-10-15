<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>随机点菜器</title>
    <style>
        #content1{
            width: 600px;
            height: 400px;
            background:#f40;
            margin: 100px auto;
            text-align: center;
            position: relative;
        }   

        #content2{
            width: 350px;
            height: 150px;
            background-color: #ccc;
            margin: auto;
            top: 0;
            left: 0;
            right: 0;
            bottom:90px;
            text-align: center;
            position: absolute;
            line-height: 100px;
            font-size:50px;

        }

        #btn{
            background: rgb(1, 46, 4);
            width: 180px;
            height: 80px;
            font-size: 30px;
            color: #0d0e0dda;
            border-radius: 12px;
            position: absolute;
            bottom: 30px;
            left: 50%;
            margin-left: -90px;
            
        }
    
    </style>
</head>
<body>
    <div id="content1">
        <div id="content2">
            <span id="span">
                随机点菜器
            </span> 
        </div>
        <button id="btn">
            开始
        </button>

    </div>

    <script>
        var arr = ['章鱼小丸子','螺丝粉','南昌拌粉','酸辣粉','黄焖鸡','麻辣烫','烧烤','花甲粉','煲仔饭','炸鸡汉堡','拉面','酸菜鱼','火锅','自助','烧腊饭','寿司','盖浇饭','华莱士'];
        var btn = document.getElementById('btn');
        var content = document.getElementById('content');
        var span = document.getElementById('span');
        var timer;//计时器
        var testNum = true;
        btn.onclick = function(){
            if(testNum){
                // console.log(1);
                start();
                btn.innerHTML = '停止';
                btn.style.backgroundColor = "#DD001B";
                testNum = false;
            }
            else{
                // console.log(0);
                stop();
                btn.innerHTML = '开始';
                btn.style.backgroundColor ="";
                testNum = true;
            }
        }
        function start(){
                timer = setInterval(function(){
                    var num = random(0,arr.length - 1);
                    span.innerHTML = arr[num];
                },50)
        }
        function stop(){
                clearInterval(timer);      
        }
        // 随机函数
        function random(a,b){
            var randomNum = Math.round(Math.random() * (b - a) + a);
            return randomNum;
        }        
    </script>
</body>
</html>
