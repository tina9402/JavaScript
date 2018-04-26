# -<!DOCTYPE html>
<html lang="cn">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>

        #all {
            padding: 80px;
            overflow: hidden;
        }

        #min, #max {
            float: left;
            width: 350px;
            height: 350px;
            position: relative;
            margin-left: 20px;
            border: 1px solid black;
        }

        #square {
            width: 100px;
            height: 100px;
            background-color: #7E7C7C;
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0.5;
            display: none;

        }

        #max {
            display: none;
            overflow: hidden;
        }

        #maxImg {
            position: absolute;
        }
    </style>
</head>
<body>
<div id="all">
    <div id="min">
        <img src="../img/min.jpg"/>
        <div id="square"></div>
    </div>
    <div id="max">
        <img src="../img/max.jpg" alt="" id="maxImg"/>

    </div>
</div>
<script>
    var oMin = document.getElementById("min");
    var oSquare = document.getElementById("square");
    var oMax = document.getElementById("max");
    var oMaxImg = document.getElementById("maxImg");
    oMin.onmouseover = function () {

        oSquare.style.display = "block";
        oMax.style.display = "block";
    }
    oMin.onmouseout = function () {

        oSquare.style.display = "none";
        oMax.style.display = "none";
    }
    document.onmousemove = function (ev) {
        var ev = ev || window.event;
        var maxL = oMin.clientWidth - oSquare.offsetWidth;
        var maxT = oMin.clientHeight - oSquare.offsetHeight;

        var mX = ev.pageX - oMin.offsetLeft - oSquare.clientWidth / 2;
        var mY = ev.pageY - oMin.offsetTop - oSquare.clientHeight / 2;


//临界值判断
        if (mX > maxL) {
            mX = maxL;
        }
        if(mX < 0) {
            mX = 0;
        }
        if (mY > maxT) {
            mY = maxT;
        }
        if (mY < 0) {
            mY = 0;
        }

        oSquare.style.left = mX + "px";
        oSquare.style.top = mY + "px";

        //比例系数
        var radioX = mX / maxL;
        var radioY = mY / maxT;

        oMaxImg.style.left = (oMax.clientWidth - oMaxImg.offsetWidth) * radioX + "px";
        oMaxImg.style.top = (oMax.clientHeight - oMaxImg.offsetHeight) * radioY + "px";
    }

</script>

</body>
</html>
