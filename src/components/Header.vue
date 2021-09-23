<template>
  <div class="header px-3 py-2 d-flex justify-content-between">
      <img src="../assets/spotify-logo.png" alt="">

      <div class="search d-flex justify-content-center align-items-center"  >

            <select name="genere" id="genere" class="px-3 py-1 me-2 rounded-1 search" v-model="genreSelected" 
            @change="getGenre" >
                <option value="all">all</option>
                <option v-for="(genre,index) in geners" :key="index" :value="genre">
                    {{genre}}

                </option>
            </select>

      </div>
  </div>
</template>

<script>

export default {
  name: 'Header',
  props: ["discList"],
  data(){
    return {
      genreSelected:"all",
    }
  },
  methods: {
    getGenre() {
      this.$emit("getGenre", this.genreSelected);
    },
  },
  computed:{
    geners(){
      const genres=[];
      this.discList.forEach((album)=>{
        if(!genres.includes(album.genre)){
          genres.push(album.genre);
        }
      })
      return genres;
    },
  },
}
</script>

<style lang="scss">
@import '../styles/general.scss';
    .header {
        width: 100vw;
        background-color: $light-greysh;
        

        img {
            width: 50px;
            height: 50px;
        }
        .search {
            font-size: 16px;
           
        
             button {
                    background-color: rgb(10, 180, 101);
                    color: #fff;
                    border: none;
                    font-size: 16px;
            }
        }


        
    }

</style>