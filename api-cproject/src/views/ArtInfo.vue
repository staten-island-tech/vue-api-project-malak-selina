<template>
  <div class="info">
    <h2>{{ art.data.title }}</h2>
     <h2>{{ art.data.department_title }}</h2>
    <div class="chart">
        <div class="leftchart">
            <ul>
                <li class="left">Artist</li>
                <li class="left">Title</li>
                <li class="left">Origin</li>
                <li class="left">Date</li>
                <li class="left">Medium</li>
            </ul>
        </div>
        <div class="rightchart">
            <ul>
                <li class="right">{{ art.data.artist_title }}</li>
                <li class="right">{{ art.data.title }}</li>
                <li class="right">{{ art.data.place_of_origin }}</li>
                <li class="right">{{ art.data.date_end }}</li>
                <li class="right">{{ art.data.medium_display }}</li>
            </ul>
        </div>
    </div>

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
    .chart{
        display: flex;
        
    }
    ul{
        list-style-type: none;
    }
    .leftchart,
    .rightchart{
        display:flex;
        flex-direction: column;

    }
</style>