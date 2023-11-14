<template>
  

<!DOCTYPE html>
<html lang="ja">
<head>

</head>
<body>
    <header>
        
    </header>




    <main>
       <canvas id= mycanvas width= 400 height= 400></canvas>

       <script>
       var canvas = document.getElementById("myCanvas");
        var context = canvas.getContext("2d");

        // マウスがクリックされたかどうかのフラグ
        var isDrawing = false;

        // 描画の開始座標
        var lastX = 0;
        var lastY = 0;

        // 描画スタイルの設定
        context.strokeStyle = "#000";  // 描画の色
        context.lineWidth = 2;         // 線の太さ

        // マウスボタンが押されたときの処理
        canvas.addEventListener("mousedown", function(e) {
            isDrawing = true;
            [lastX, lastY] = [e.clientX - canvas.offsetLeft, e.clientY - canvas.offsetTop];
        });

        // マウスが移動したときの処理
        canvas.addEventListener("mousemove", function(e) {
            if (!isDrawing) return;  // マウスボタンが離れている場合は処理しない

            // 線を描画
            context.beginPath();
            context.moveTo(lastX, lastY);
            [lastX, lastY] = [e.clientX - canvas.offsetLeft, e.clientY - canvas.offsetTop];
            context.lineTo(lastX, lastY);
            context.stroke();
        });

        // マウスボタンが離れたときの処理
        canvas.addEventListener("mouseup", function() {
            isDrawing = false;
        });

        // マウスがCanvasを離れたときの処理
        canvas.addEventListener("mouseout", function() {
            isDrawing = false;
        });
       
       </script>

    </main>




    <footer>
        <p>&copy; 2023 サイト名. All Rights Reserved.</p>
    </footer>
</body>
</html>
</template>