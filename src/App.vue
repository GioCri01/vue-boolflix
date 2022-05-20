<template>
  <div>
    <HeaderComp @search="findMovies"/>
    <MainComp
    
    :movieList="arrMovies"
    
    />
  </div>
</template>

<script>
import axios from "axios";
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
  },
  data(){
    return{
      baseApi: "https://api.themoviedb.org/3/search/movie?api_key=c182b8dc206ed121416b5cf16ae6a95c&language=it-IT",
      arrMovies: [],
      query:"",
      

    }
  },
  

  methods:{
    getApi(){
      axios.get(this.baseApi,{
        params:{
          query: this.query
        }
      })
      .then(res =>{
        
        this.arrMovies = res.data.results
        console.log(this.arrMovies);
      })
    },
    findMovies(searchMovie){
        this.query = searchMovie
        this.getApi()
        console.log(this.query);
      

    }

    

  },

  
}
</script>


<style lang="scss">
@import "./assets/style/general";
</style>
