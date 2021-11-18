<template>
  <div class="info">
    <p>{{ this.art.title }}</p>
  </div>
</template>

<script>
import ArtList from '@/views/ArtList.vue'
export default {
    props: ['id'],
    data(){
        return {
            art:{}
        }
    },
    created(){
        ArtList.getArt(this.id)
        .then(response => {
            this.art = response.data
        })
        .catch( error => {
            console.log('error smh:', error.response)
        })
    }
}
</script>

<style scoped>
/* 
div{
    display: flex;
    justify-content: center;
    align-items: center;
} */

</style>