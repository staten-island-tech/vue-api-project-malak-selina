<template>
  <div>
      <h1>Artworks</h1>
  </div>
</template>

<script>
export default {
    data(){
        return{
            art:[]
        }
    },
    created(){
        fetch('https://api.artic.edu/api/v1/artworks/129884')
        .then(response => response.json())
        .then(response => {
            console.log(response);
            this.art = response.data
        })
        .catch(err => {
            console.log(err.response, 'There is an error!');
        })
    }
}
</script>

<style>

</style>