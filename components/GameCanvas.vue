<template>
<div>
  <canvas id="gameCanvas" width="800" height="600"></canvas>
  </div>
  </template>
  
  <script>
  export default {
    mounted() {
      this.initGame();
  },
    methods: {
      initGame() {
        const canvas = this.$el.querySelector('#gameCanvas');
        const ctx = canvas.getContext('2d');

        class Player
         {constructor(x, y) {
          this.x = x;
          this.y = y;
          this.width = 50;
          this.height = 50;
          this.color = 'blue';
        }

        draw() {
          ctx.fillStyle = this.color;
          ctx.fillRect(this.x, this.y, this.width, this.height);
        }

        move(dx, dy) {
          this.x += dx;
          this.y += dy;
          this.draw();
        }
      }
      const player = new Player(100, 100);

      const gameLoop = () => {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        player.draw();
        requestAnimationFrame(gameLoop);
      };

      gameLoop();

      const handleKeyDown = (event) => {
        switch (event.key) {
          case 'ArrowLeft':
            player.move(-10, 0);
            break;
          case 'ArrowRight':
            player.move(10, 0);
            break;
          case 'ArrowUp':
            player.move(0, -10);
            break;
          case 'ArrowDown':
            player.move(0, 10);
            break;
        }
      };

      window.addEventListener('keydown', handleKeyDown);

      // イベントリスナーをクリーンアップ
      this.$once('hook:beforeDestroy', () => {
        window.removeEventListener('keydown', handleKeyDown);
      });
    }
  }
};
</script>

<style>/* 必要に応じてスタイルを追加 */</style>