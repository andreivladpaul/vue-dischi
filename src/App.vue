<template>
  <div id="app">
    <Header />
    <Discs />
    
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Discs from './components/Discs.vue'

export default {
  name: 'App',
  components: {
    Header,
    Discs
  }
}
</script>

<style lang="scss">
#app {
  width: 100vw;
  height: 100vh;
}

</style>
