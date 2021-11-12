<template>
  <div>
      <h1>Artworks</h1>
      <ArtPiece v-for="art in arts" :key="art.id" :art="art"/>
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
            arts:[]
        }
    },
    created(){
        fetch('https://api.artic.edu/api/v1/artworks?page=2&limit=100')
        .then(response => response.json())
        .then(response => {
            console.log(response.data);
            this.arts = response.data
        })
        .catch(err => {
            console.log(err.response, 'There is an error!');
        })
    }
}
</script>

<style>

</style>