<template>
  <div class="info">
    <p>{{ this.arts.title }}</p>
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
         getArts() {
         return this.arts.get('/informations')
        },
        getArt: function(id){
            return this.arts.id.get('/information/' + id)
        },
        
    }
}
</script>

<style scoped>
<<<<<<< HEAD
    .info{
        color:black;
    }
=======
/* 
div{
    display: flex;
    justify-content: center;
    align-items: center;
} */

>>>>>>> 35c12297991f68fa977f3a85fe8cfbf979b02a3f
</style>