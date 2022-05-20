<template>
  <div>
    <HeaderComp/>
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

    }
  },
  mounted(){
    this.getApi()
  },

  methods:{
    getApi(){
      axios.get(this.baseApi,{
        params:{
          query: "harry potter"
        }
      })
      .then(res =>{
        
        this.arrMovies = res.data.results
        console.log(this.arrMovies);
      })
    }
  }
}
</script>


<style lang="scss">
@import "./assets/style/general";
</style>
