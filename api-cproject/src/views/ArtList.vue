<template>
<div class="all">
    <h1>Artworks</h1>
  <div class="art-list">
      <ArtPiece v-for="art in arts" :key="art.id" :art="art"/>
  </div>
</div>
</template>

<script>
import ArtPiece from '@/components/ArtPiece.vue'
export default {
    components: {
        ArtPiece
      },
    data(){
        return{
            arts:[],
        }
    },
    created(){
        fetch("https://api.artic.edu/api/v1/artworks?page=2&limit=32")
        .then(response => response.json())
        .then(response => {
            console.log(response.data);
            this.arts = response.data
        })
        .catch(err => {
            console.log(err.response, 'There is an error!');
        })
    },
    computed:{
        getArt: function(id){
            return this.arts.id.get('/artworks/' + id)
        }
    }
}
</script>

<style>
.art-list{
    display:flex;
    width:90vw;
    flex-wrap: wrap;
    margin:0 auto;
    justify-content: space-around;
    align-items: center;
}
img{
    width:20vw;
}
</style>