<template>
  <div>
      <img :src="art.thumbnail.lqip" alt="art image" :key="art.id" :art="art" class="picture">
  </div>
</template>

<script>
export default {
    props:{
        art: Object
    }
}
</script>

<style>
    img{
        width:10rem;
    }
</style>