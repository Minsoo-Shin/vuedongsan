<template>
    <div>
        <img :src="roomObj.image" class = "room-img"> 
        <h4 @click="send()">{{ roomObj.title }}</h4>
        <p> {{roomObj.price}}원 </p>
    </div>
</template>

<script>
export default {
    name: "Product",
    data(){
        return {
            product_count : 0
        }
    },
    props : {
        roomObj : Object,
    },
    method : {
        send(){
            this.$emit('openModal', this.roomObj.id)
        }
    }
}
</script>

<style>

</style>