<template>
  <div id="app">
    <Header 
      :discList="disclist"
      @getGenre="getGenre" 
    />
    <Discs 
      :discList="disclist"
      :filtergener="filtergener"
     />
    
    
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Discs from './components/Discs.vue'


export default {
  name: 'App',
  components: {
    Header,
    Discs
  },
  data(){
    return {
      disclist:[],
      filtergener:"all",
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
     
      
      
    }
  },
  created(){
    this.getdisc();
  },
  methods:{
    getdisc(){
      axios.get(this.APIUrl).then( res=>{
        this.disclist = res.data.response;
        
      })
    },
    getGenre(gener){
      this.filtergener=gener;
    }
  }
}
</script>

<style lang="scss">
#app {
  width: 100vw;
  height: 100vh;
}

</style>
