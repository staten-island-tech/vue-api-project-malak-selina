<template>
  <div class="info">
    <h2 class="artname">{{ art.data.title }}</h2>
    <div class="middle">
        <router-link to="/list">
      <button class="btn"> Back </button>
      </router-link>
          <span class="red"></span>
    </div>
     <h4 class="genre">{{ art.data.department_title }}</h4>
    <img src="this.specificImage" alt="">
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
            specificImage: {},
        }
    },
    methods:{
        async getData(){
            const data = await fetch( `https://api.artic.edu/api/v1/artworks/${this.id}`);
            const response = await data.json();
            this.art = response
            console.log(response)
        },
        async getSpecificImage(){
            const painting = await fetch(`https://www.artic.edu/iiif/2/${this.image_id}/full/500,/0/default.jpg`);
            const result = await painting.json();
            this.specificImage = result
        }
    },
    created(){
        this.getData()
        this.getSpecificImage()
    },  


}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
    .info{
        color:black;
        font-family: 'Roboto', sans-serif;
    }
    .chart{
        display: flex;
        margin:0 auto;
        justify-content: center;
        align-items: center;
        width:70vw;
        height: 50vh;
        border:black .1rem;
    }
    ul{
        list-style-type: none;
    }
    li{
        margin-bottom:1rem;
    }
    .leftchart,
    .rightchart{
        display:flex;
        flex-direction: column;
        font-size: 1rem;
    }
    .leftchart{
        font-weight: 900;
        border-right: .1rem solid gray;
        padding:1rem;
    }
    .rightchart{
        font-style: oblique;
    }
    .artname{
        margin-top:1.5rem;

    }
    .genre{
        color:gray;
        text-transform:uppercase;
    }
    .btn{
        background-color: white;
        color: black;
        border: 2px solid black; 
        padding:.5rem;
        font-weight: 600;
        margin-left:0;
    }
    .middle{
        display:flex;
        align-items: center;
        margin:0 auto;
        justify-content: center;
        width:70vw;
    }
    .red{
    width:50px;
    height:5px;
    margin-top:.5rem;
    background-color: red;
    border-radius: 5px;
    color:red;
    margin-left:10rem;
    margin-right:20%;
}
</style>