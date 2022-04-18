<template>

<Modal @closeModal="modalOpen=false" :roomObjArr="roomObjArr" :roomId="roomId" :modalOpen="modalOpen"/>

<!-- 배너 -->
<div class = "menu">
  <a v-for="i in menus" :key ="i">{{ i }}</a>  
</div>

<Discount/>
<!-- 본문 -->
<Product @openModal="modalOpen=true; roomId = $event" :roomObj="roomObj" v-for="roomObj in roomObjArr" :key ="roomObj"/>

</template>

<script>
import {roomObjArr} from "./assets/oneroom.js";
import Discount from "./Discount.vue";
import Modal from "./Modal.vue";
import Product from "./Product.vue"

export default {
  name: 'App',
  data(){
    return {
      roomObjArr,
      roomId : 0,
      // 신고수 : [0,0,0],
      menus : ['Home', 'Product', 'About'],
      // products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      // img : ['./assets/room0.jpeg', './assets/room1jpeg', './assets/room2.jpeg'],
      modalOpen : false,
      count : 0
    }
  },
  method : {
    increase(id) {
      this.신고수[id] += 1;
    },
  },
  components: {
    Discount : Discount,
    Modal : Modal,
    Product : Product,
  }
}
</script>

<style>
body {
  margin : 0;
}
div {
  box-sizing : border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width : 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color : white;
  padding : 20px;
}

.room-img {
  width : 100%;
  margin-top : 40px;
}

.close{
  width :5%;
  position: absolute;
  top: 0; right: 0;
  background: white;
}
</style>
``