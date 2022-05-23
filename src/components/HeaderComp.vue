<template>
  <header>
      <div class="container-fluid d-flex justify-content-between align-items-center">
          <img src="https://www.romait.it/wp-content/uploads/2022/04/Netflix-logo.jpg" alt="">
          <div class="d-flex ">
              <select 
              v-model="selectedOption"
               @change="$emit('filter',selectedOption )"
                class="form-control">
                    <option disabled value="" >Filtra per Genere:</option>
                  <option value="movie" selected >film</option>
                  <option  value="tv">serie Tv</option>
              </select>
              <input @keyup.enter="$emit('search',searchMovie)" v-model.trim="searchMovie" type="text" placeholder="cerca film" class="form-control mx-2">
              <button @click="$emit('search',searchMovie)" class="btn bg-danger" > Cerca</button>
          </div>
      
  </div>
  </header>
</template>

<script>
export default {
    name: "HeaderComp",

    data(){
        return{
            searchMovie:"",
            selectedOption :""
        }
    }

}
</script>

<style lang="scss" scoped>
header{
    height: 100px;
    background-color: black;
    img{
        width: 175px;
    }
    
}


</style>


