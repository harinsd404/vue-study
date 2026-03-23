<template>
  <Modal v-if="모달창" :원룸들="원룸들" :상품번호="상품번호" @close="모달창=false" />
  <div class="app">
    <nav class="menu">
      <a v-for="(작명1, 작명2) in 메뉴들" :key="작명2">{{ 작명1 }}</a>
    </nav>
    <Card v-for="(원룸, index) in 원룸들" :key="index" :room="원룸" @open="상품번호=index; 모달창=true" />
  </div>
</template>

<script>
import data from './assets/oneroom';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  components: {
    Modal,
    Card,
  },
  data() {
    return {
      상품번호: 0,
      원룸들: data,
      모달창: false,
      신고수: [0,0,0,0,0,0],
      메뉴들: ['Home', 'Shop', 'About'],
      price1: 100,
      price2: 200,
      price3: 300,
      products: ['해운대원룸', '에코델타시티원룸', '광안리원룸'],
    }
  },
  methods: {
    increase() {
      this.신고수 += 1;
    }
  },
}
</script>
