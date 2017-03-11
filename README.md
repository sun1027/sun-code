# sun-code
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>canvas</title>
    <style type="text/css">
        #canvas{
            border:1px solid #000000;
        }
    </style>
</head>
<body>
<canvas id="canvas" width="800" height="800"></canvas>
</body>
<script>
    window.onload=function() {
        var canvas = document.getElementById("canvas");//获取canvas的ID
        var context = canvas.getContext("2d");//这句话的作用相当于添加强大的绘图工具
        /* context.lineWidth=10;//设置线条的粗细
      context.strokeStyle="red";//设置线条的颜色
      context.lineCap="round";//把线头的形状变成圆形，也有长方头，默认是butt
      context.moveTo(10,10);//确定点的开头的坐标
      context.lineTo(400,400);//确定点的结束的坐标
      context.stroke();//画出线来
        //绘图的另一个特性beginPath(),作用是重新开始新的线段的绘制
        context.beginPath();
        context.moveTo(20,200);//确定点的开头的坐标
        context.lineTo(400,400);//确定点的结束的坐标
        context.stroke();//画出线来
        context.closePath();*/
        context.moveTo(250,50);
        context.lineTo(50,250);
        context.lineTo(450,250);
        context.closePath();//closePath 会在最后一个绘制点和绘制的起点之间绘制一条线；
        //填充内部
        context.fillStyle="blue";
        context.fill();
        //填充外部的轮廓
        context.strokeStyle="green";
        context.stroke();
        context.beginPath();
        context.strokeStyle="black";
        context.strokeRect(50,20,34,34);
        context.stroke();
        //建议先填充颜色，再去填充轮廓，不这样的话，轮廓的颜色可能会被覆盖点；
        context.beginPath();
       var centerX=350;
       var
               centerY = 300;
        var radius= 100;
        var startingAngle=0.5*Math.
                PI;
        var endingAngle=1*Math.PI;
       context.arc(centerX,centerY,
               radius, startingAngle, endingAngle);
        context.stroke();
        context.beginPath();
        //在三个地方绘制同样大小的的正方形
        context.rect(400,400,30,30);
        context.rect(450, 450,30,30);
        context.rect(500, 500,30,30);
        context.strokeStyle= "red";
        context.translate(20,20);
        context.rect(400,400,30,30);
        context.translate(10,10);
        context.rect(450,450,30,30); //
        //translate是移动了坐标的原点；
        // 要注意的一点是translate（平移）和rotate（旋转）都是具有累加的机制，
        context.stroke();
        context.beginPath();
        context.translate(600,600);
         var num=10;
        for(var i=1;i<num;i++) {
            context.rotate(2 * Math.PI / (num-1));
            //在绘制正方形的时候要先旋转坐标，旋转一周是2*Math.PI,因此每个正方形的旋转角度取决于要绘制的总是
            //rotate的使用方法context.rotate(angle);如需将角度转换为弧度，请使用 degrees*Math.PI/180 公式进行计算。
            context.rect(0, 0, 50, 50);
        }
        context.stroke();
        context.beginPath();
        //接下来介绍的是透明度；
        context.fillStyle="rgba(100,100,100,0.5)";//只是设置了一种样式的透明度；
        context.globalAlpha=0.5;//这个透明度的作用是将所有的样式的透明度设置为一样的；
       //canvas的合成操作，一般在canvas 中绘制多个图形时候，后面绘制的图形会位于先绘制的图形的上面，为遮住原来绘制的图形，
        //默认的合成操作是source-over,即新绘制的图形位于先绘制的图形上面，还会有覆盖；，改变合成的操作添加context.globalCompositeOperation=""
        context.globalCompositeOperation="orx";//orx是告诉浏览器不显示两个图形相互重叠的部分

      }
</script>
</html>
