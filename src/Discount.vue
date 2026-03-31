<template>
     <div class="discount">
      <h4>지금 결제하면 {{count}}% 할인</h4>
    </div>
</template>

<script>
export default {
  name: 'Discount',
  data(){
    return{
        count: 5
    }
  },
  mounted(){
    this.discount = setInterval(()=>{
        this.count--;
        if(this.count <= 0){
            this.stopInterval();
        }
    }, 1000)
  }, methods: {
    stopInterval(){
        clearInterval(this.discount);
    }
  }
}
</script>