<template>
  <div class="app">
    <nav class="menu">
      <a v-for="(작명1,작명2) in 메뉴들" :key="작명2">{{작명1}}</a>
    </nav>

    <main class="content">
      <img src="./assets/logo.svg" alt="logo" class="logo" />

      <div class="product-card">
        <h4>{{ products[0] }}</h4>
        <p>{{ price1 }} 만원</p>
        <button @click="increase(0)"> 허위매물신고</button> <span>신고수: {{ 신고수[0] }}</span>
      </div>

      <div class="product-card">
        <h4>{{ products[1] }}</h4>
        <p>{{ price2 }} 만원</p>
        <button @click="increase(1)"> 허위매물신고</button> <span>신고수: {{ 신고수[1] }}</span>
      </div>

      <div class="product-card">
        <h4>{{ products[2] }}</h4>
        <p>{{ price3 }} 만원</p>
        <button @click="increase(2)"> 허위매물신고</button> <span>신고수: {{ 신고수[2] }}</span>
      </div>
    </main>
  </div>
</template>

<script>

export default {
  name : 'App',
  data(){
    return {
      신고수 : [0, 0, 0],
      메뉴들 : ['Home', 'Shop', 'About'],
      price1 : 100,
      price2 : 200,
      price3 : 300,
      products : ['해운대원룸', '에코델타시티원룸', '광안리원룸'],
    }
  },
  methods : {
    increase(num){
      this.신고수[num] += 1;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background: #f5f5f7;
}

.app {
  min-height: 100vh;
}

.menu {
  background-color: #43358a;
  padding: 15px 40px;
  display: flex;
  gap: 24px;
  align-items: center;
}

.menu a {
  color: white;
  text-decoration: none;
  font-weight: 600;
  font-size: 16px;
}

.menu a:hover {
  opacity: 0.8;
}

.content {
  max-width: 900px;
  margin: 40px auto;
  padding: 0 24px 40px;
}

.logo {
  width: 100px;
  margin-bottom: 24px;
}

.product-card {
  background: white;
  border-radius: 8px;
  padding: 16px 20px;
  margin-bottom: 16px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.06);
}

.product-card h4 {
  margin-bottom: 8px;
  font-size: 18px;
}

.product-card p {
  margin: 0;
  color: #555;
}
</style>