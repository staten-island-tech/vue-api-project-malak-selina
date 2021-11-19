<template>
  <div class="gallery">
      <router-link :to="{ name:'ArtInfo', params: { id:art.id} }">
      <img :src="image" :alt="art.thumbnail.alt_text" :key="art.id" :art="art" class="picture">
      <p class="title">{{ art.title }}</p>
      </router-link>
  </div>
</template>

<script>
export default {
    props:{
        art: Object,
        id: Number,
    },
     computed: {
        image: function(){
            return `https://www.artic.edu/iiif/2/${this.art.image_id}/full/500,/0/default.jpg`;
        },
    }, 

}
</script>

<style scoped>
    .gallery{
        position: relative;
    }
    img{
        width:10rem;
        margin-bottom: 2rem;
        box-shadow: 0 1.5rem 1rem rgba(0, 0, 0, 0.4);
        outline-offset: 0.5rem;
        transition: all 0.5s;
    }
        .title{
        font-size:3rem;
        opacity:0;
        color:#000;
        position:absolute;
        top:50%;
        left:50%;
        transform:translate(-50%, -250%);
        transition:all .5s;
    }
    img:hover{
        transform: scale(1.1);
        box-shadow:0 3rem 1rem rgba(0, 0, 0, 0.4);
    }

    img:hover .title{
        opacity:1;
        top:50%;
    }
</style>