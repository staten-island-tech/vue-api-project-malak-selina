<template>
  <div>
      <img src="https://www.artic.edu/iiif/2/${arts.image_id}/full/843,/0/default.jpg" :alt="art.thumbnail.alt_text" :key="art.id" :art="art" class="picture">
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