<template>
  <div>
    <HeaderComp 
    @search="findMovies"
    @filter="ChangeOption"
    :popularApi="getDefaultAPI"
    
    />
    <MainComp
    
    :movieList="arrMovies"
    :FilterValue="optionValue"
    
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
      baseApiTv:"https://api.themoviedb.org/3/search/tv?api_key=c182b8dc206ed121416b5cf16ae6a95c&language=it-IT",
      arrMovies: [],
      query:"",
      optionValue:"",

      
      

    }
  },

  mounted(){
    this.getDefaultAPI()
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
        
      })
    },

    getApiTv(){
      axios.get(this.baseApiTv,{
        params:{
          query: this.query
        }
      })
      .then(res =>{
        
        this.arrMovies = res.data.results
        
      })
    },

    findMovies(searchMovie){
        this.query = searchMovie
        this.getApi()
        if(this.query === ""){
          this.getDefaultAPI()
        }else if(this.optionValue === "movie"){
           this.getApi()
           
        }else {
          this.getApiTv()
          
        }
        
      

    },
    getDefaultAPI(){
      axios.get("https://api.themoviedb.org/3/movie/popular?api_key=c182b8dc206ed121416b5cf16ae6a95c&language=it-IT")
      .then(res=>{
        this.arrMovies = res.data.results
      })
    },

    ChangeOption(selectedOption){
      this.optionValue = selectedOption
      console.log(this.optionValue);

    }



    

  },

  
}
</script>


<style lang="scss">
@import "./assets/style/general";
</style>
