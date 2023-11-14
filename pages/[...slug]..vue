
<template>
  <div>
    <h1>Vue.js Canvas Apphsjsj</h1>
    <canvas ref="myCanvas" width="400" height="400"></canvas>
  </div>
  
</template>

<script>
export default {
  mounted() {
    const canvas = this.$refs.myCanvas;
    const context = canvas.getContext("2d");

    // マウスクリックイベントをリッスン
    canvas.addEventListener("click", (event) => {
      const x = event.clientX - canvas.getBoundingClientRect().left;
      const y = event.clientY - canvas.getBoundingClientRect().top;

      // クリックした位置に円を描画
      context.beginPath();
      context.arc(x, y, 20, 0, 2 * Math.PI);
      context.fillStyle = "blue";
      context.fill();
      context.closePath();
    });
  },
};
</script>


