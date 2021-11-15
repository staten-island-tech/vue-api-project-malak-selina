<template>
  <div>
    <h1>{{ art.artist_title }}</h1>
      <!-- <img :src="art.thumbnail.lqip" alt="art image" :key="art.id" :art="art" class="picture"> -->
      <!-- <img :src="image.iiif_url"> -->
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