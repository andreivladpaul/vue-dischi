<template>
  <div class="disc text-center p-2">
      <a href="#">
          <img class="img-fluid mb-1" :src="info.poster" :alt="info.title">
      </a>
      <p class="f-big mb-1 title text-uppercase font-weight-bold text-white">{{ info.title }}</p>
        <p class="author f-med mb-1">{{ info.author }}</p>
        <p class="fw-bold f-sm mb-1 year">{{ info.year }}</p>
  </div>
</template>

<script>
export default {
    name: 'SingleDisc',
    props: ['info']

}
</script>

<style lang="scss">
@import '../styles/general.scss';
.disc {
    background-color: $light-greysh;
    .title {
        font: 600;
    }
    .author, .year {
        color: #808080 ;
    }
    a > img {
        min-width: 185px;
        min-height: 186px;
    }

    
    
}

</style>