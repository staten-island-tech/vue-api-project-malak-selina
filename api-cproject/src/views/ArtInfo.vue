<template>
  <div class="info">
    <p>{{ this.art.title }}</p>
  </div>
</template>

<script>
import ArtPiece from '@/components/ArtPiece.vue'
export default {
    props: ['id'],
    data(){
        return {
            art:{},
        }
    },
    created(){
        ArtPiece.getArt(this.id)
        .then(response => {
            this.art = response.data
        })
        .catch( error => {
            console.log('error smh:', error.response)
        })
    },
    methods:{
        /*  getArts() {
         return this.art.get('/information')
        }, 
         getArt: function(id){
            return this.art.id.get('/information/' + id)
        }, */
        
    }
}
</script>

<style scoped>
    .info{
        color:black;
    }
</style>