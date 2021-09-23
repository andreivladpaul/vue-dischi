<template>
  <section class="discs clearfix ">
      <div class="container px-5 py-5">
        <div  class="row ">
            <!-- Stampo la lista dei dischi ottenuta tramite Axios API --> <!-- col-6 col-md-4 -->
            <div v-for="(disc, index) in filterlist" :key="index" class=" disc col mx-1 mb-4">
                <Disc :item="disc" />
            </div>
        </div> 
      </div>
  </section>
</template>

<script>
import Disc from './Disc.vue'

export default {
  name: 'Discs',
  props: ["discList","filtergener"],
  components: {
    Disc,
   
  },
  data(){
    return {
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
    }
  },
  computed:{
    filterlist(){
      let filterlist=this.discList.filter((ris)=>{
        if(this.filtergener=="all") return true
        else if(ris.genre==this.filtergener)return true;
        else return false;
      });
      return filterlist;
    }
  }
}
</script>

<style lang="scss">
@import '../styles/general.scss';
.discs {
    background-color: $dark-greysh ;
    width: 100%;
    height: 100%;

    .disc {
        min-width: 200px;
        min-height: 360px;
    }
}

</style>