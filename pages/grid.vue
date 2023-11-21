<template>
  <div class="container">
    <div class="title">
      <p>キャラクター選択</p>
    </div>

    <div class= chose>
      <div class="kyara onep"></div>
      <div class="kyara secp"></div>
    </div>

    <div       class="chose">
      <div class="btn square">
        <img width="100" height="100" src="/suika.jpg" alt="スイカ">
      </div>
      <div class="btn square">
        <img width="100" height="100" src="/jagaimo.jpg" alt="じゃがいも">
      </div>
      <div class="btn square">
        <img width="100" height="100" src="/banana.jpg" alt="バナナ">
      </div>
      <div class="btn square">
        <img width="100" height="100" src="/piman.jpg" alt="ピーマン">
      </div>
      <div class="btn square">
        <img width="100" height="100" src="/onigiri.jpg" alt="おにぎり">
      </div>
      <div class="btn square">
        <img width="100" height="100" src="/ninniku.jpg" alt="にんにく">
      </div>
    </div>
  </div>
</template>

<script>

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
