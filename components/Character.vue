<template>
<div class= chose>
    <div class="kyara onep"></div>
    <div class="kyara secp"></div>
</div>

<div class="chose">
    <div class="btn square">
      <img width="100" height="100" src="../public/suika.jpg" alt="スイカ">
    </div>
    <div class="btn square">
      <img width="100" height="100" src="../public/jagaimo.jpg" alt="じゃがいも">
    </div>
    <div class="btn square">
      <img width="100" height="100" src="../public/banana.jpg" alt="バナナ">
    </div>
    <div class="btn square">
      <img width="100" height="100" src="../public/piman.jpg" alt="ピーマン">
    </div>
    <div class="btn square">
      <img width="100" height="100" src="../public/onigiri.jpg" alt="おにぎり">
    </div>
    <div class="btn square">
      <img width="100" height="100" src="../public/ninniku.jpg" alt="にんにく">
    </div>
  </div>
</template>

<style scoped>
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