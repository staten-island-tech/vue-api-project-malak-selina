<template>
  <div class="info">
      
    <h2>{{ art.data.artist_title }}</h2>
  <ul><li v-for="cat in art.data.category_ids" :key="cat">{{cat}}</li></ul>
  </div>
</template>

<script>
// import ArtPiece from '@/components/ArtPiece.vue'
// import ArtList from '@/views/ArtList.vue'
export default {
    props: ['id'],
    data(){
        return {
            art:{},
        }
    },
    methods:{
        async getData(){
            const data = await fetch( `https://api.artic.edu/api/v1/artworks/129884`);
            const response = await data.json();
            this.art = response
            console.log(response)
        }
    },
    created(){
        this.getData()
    },  
    // getArts() {
    //     return this.arts.get('/information')
    //  },
    // getArt(id) {
    //     return this.arts.get('/information/' + id)
    // },

}
</script>

<style scoped>
    .info{
        color:black;
    }
</style>