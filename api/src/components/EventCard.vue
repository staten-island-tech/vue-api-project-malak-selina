<template>
 <router-link class="event-link" :to="{ name:'event-show', params: { id:meme.id} }"> 
    <div class="event-card -shadow">
        <!-- <img class="eyebrow" v-bind:src="{{ meme.image }}"> -->
        <h4 class="title">{{ meme.name }}</h4>
    </div>
</router-link>
</template>
<script>
export default {
    props:{
        meme: Object
    }
}
</script>