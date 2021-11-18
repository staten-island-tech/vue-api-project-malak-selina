<template>
  <div class="info">
<p >{{ image.title }}</p>
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

<style>

</style>