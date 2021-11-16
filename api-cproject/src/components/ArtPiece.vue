<template>
  <div>
      <img :src="image" :alt="art.thumbnail.alt_text" :key="art.id" :art="art" class="picture">
  </div>
</template>

<script>
export default {
    props:{
        art: Object
    },
     computed: {
        image: function(){
            return `https://www.artic.edu/iiif/2/${this.art.image_id}/full/843,/0/default.jpg`;
        },
    }, 
}
</script>

<style>
    img{
        width:10rem;
    }
</style>