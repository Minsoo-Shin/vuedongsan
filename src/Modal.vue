<template>
<div class = "black-bg" v-if="modalOpen == true">
  <div class = "white-bg">
    <h4>{{roomObjArr[roomId].title}}</h4>
    <img :src="roomObjArr[roomId].image" class = "room-img"> 
    <p>{{roomObjArr[roomId].content}}</p>
    <p>{{roomObjArr[roomId].price}}원</p>
    <!-- <Discount/> -->
    <button @click="$emit('closeModal')">닫기</button>
  </div>
</div>
</template>

<script>
export default {
    name: "Modal",
    props : {
        roomObjArr : Array,
        roomId : Number,
        modalOpen : Boolean,
    }
}
</script>

<style>

</style>