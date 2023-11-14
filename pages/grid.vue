<template>
  <div class="container">
    <div class="title">
      <p>キャラクター選択</p>
    </div>

    <div class= chose>
      <div class="kyara onep" @drop="handleDrop" @dragover.prevent @dragenter.prevent></div>
      <div class="kyara secp" @drop="handleDrop" @dragover.prevent @dragenter.prevent></div>
    </div>

    <div class="chose">
      <div class="btn square" @dragstart="handleDragStart" draggable="true">
        <img width="100" height="100" src="./imgs/suika.jpg" alt="スイカ">
      </div>
      <div class="btn square" @dragstart="handleDragStart" draggable="true">
        <img width="100" height="100" src="./imgs/jagaimo.jpg" alt="じゃがいも">
      </div>
      <div class="btn square" @dragstart="handleDragStart" draggable="true">
        <img width="100" height="100" src="./imgs/banana.jpg" alt="バナナ">
      </div>
      <div class="btn square" @dragstart="handleDragStart" draggable="true">
        <img width="100" height="100" src="./imgs/piman.jpg" alt="ピーマン">
      </div>
      <div class="btn square" @dragstart="handleDragStart" draggable="true">
        <img width="100" height="100" src="./imgs/onigiri.jpg" alt="おにぎり">
      </div>
      <div class="btn square" @dragstart="handleDragStart" draggable="true">
        <img width="100" height="100" src="./imgs/ninniku.jpg" alt="にんにく">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleDrop(event) {
      const file = event.dataTransfer.files[0];

      if (file) {
        if (file.type.startsWith('image/')) {
          const imageUrl = URL.createObjectURL(file);
          const targetClassList = event.target.classList;
          const isOneP = targetClassList.contains('onep');
          const isSecP = targetClassList.contains('secp');

          if (isOneP || isSecP) {
            this.drawImageOnCanvas(imageUrl, isOneP ? 'onep' : 'secp');
          }
        }
      }
    },

    handleDragStart(event) {
      event.dataTransfer.setData('text/plain', event.target.innerHTML);
    },
  },

  drawImageOnCanvas(imageSrc, canvasRef) {
    const canvas = this.$refs[canvasRef];
    const context = canvas.getContext('2d');

    const image = new Image();
    image.src = imageSrc;

    image.onload = () => {
      context.clearRect(0, 0, canvas.width, canvas.height);
      context.drawImage(image, 0, 0, canvas.width, canvas.height);
    };
  },
};
</script>

<style scoped>
.container {
  height: 100%;
}

.title {
  text-align: center;
  font-size: 70px;
}

.chose {
  display: flex;
}

.kyara {
  width: 595px;
  height: 506px;
  border: 2px solid transparent;
}

.onep {
  border: 2px solid blue;
}

.secp {
  border: 2px solid red;
}

.btn {
  flex: 1;
  padding-bottom: 10%;
  padding-left: 10%;
  margin: 10px;
  width: 10%;
  height: 9px;
  border: 2px solid black;
  display: block;
}

.square {
  width: 100%;
  overflow: hidden;
}
</style>
