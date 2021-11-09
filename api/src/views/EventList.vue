<template>
  <div>
      <EventCard v-for="meme in memes" :key="meme.id" :meme="meme"/>
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
export default {
     components: {
        EventCard,
      },
      data() {
        return {
          memes: []
        }
      },
      created() {
        fetch("http://alpha-meme-maker.herokuapp.com/:page", {
            mode: "no-cors",
        })
        .then(response => {
            this.memes = response.data 
            console.log(response);
        })
        .catch(err => {
            console.error(err);
        });
      }

}
</script>

<style>

</style>