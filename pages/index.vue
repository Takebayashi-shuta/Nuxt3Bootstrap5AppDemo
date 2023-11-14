<template>
  <div>
    <p class="display-1">路地裏の戦い</p>

    <main>
      <div class="row">
        <div class="col">
          <div style="text-align: center">
            <nuxt-link to="./grid" class="btn btn-danger">プレイ</nuxt-link>
            <nuxt-link to="./game" class="btn btn-secondary">設定</nuxt-link>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style>
  .body {
    height: 100%;
  }

  .display-1 {
    text-align: center;
    padding: 200px;
    font-weight: 700;
  }

  .btn {
    padding: 10px 20px;
    font-size: 150px;
    margin: 10px;
  }
</style>
