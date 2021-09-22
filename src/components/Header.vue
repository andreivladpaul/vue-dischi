<template>
  <div class="header px-3 py-2">
      <img src="../assets/spotify-logo.png" alt="">
  </div>
</template>

<script>
export default {
    name: 'Header',
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
        
    }

</style>