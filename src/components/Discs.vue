<template>
  <section class="discs clearfix ">
      <div class="container px-5 py-5">
        <div  class="row ">
            <!-- Stampo la lista dei dischi ottenuta tramite Axios API --> <!-- col-6 col-md-4 -->
            <div v-for="(disc, index) in discsList" :key="index" class=" disc col mx-1 mb-4">
                <SingleDisc :info="disc" />
            </div>
        </div> 
      </div>
  </section>
</template>

<script>
import axios from 'axios'
import SingleDisc from './SingleDisc.vue'

export default {
    name: 'Discs',
    components: {
        SingleDisc
    },
    data() {
        return {
            APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            discsList: [],
            loader: true
        }
        
    },
    created() {
            this.getDiscs();
        },
        methods: {
            getDiscs() {
                axios
                    .get(this.APIUrl)
                    .then(res => {
                        this.discsList = res.data.response;
                    })
            },
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