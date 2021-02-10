<template>
  <h1 class="text-center w-full mt-8 h-20 f-20">{{ fullName }}</h1>
</template>

<script>
export default {
    computed:{
        fullName() {
            return `${this.shopName} ${this.shopType}`;
        },
    },
    data(){
        return{
            shopName: "Pet",
            shopType: "Shop",
        }
    }
}
</script>

<style>

</style>