<template>
  <div class="disc text-center pt-3 ">
      <a href="#">
          <img class="img-fluid mb-1" :src="item.poster" :alt="item.title">
      </a>
      <p class="title f-big mb-1  text-uppercase font-weight-bold text-white">{{ item.title }}</p>
        <p class="author f-med mb-1">{{ item.author }}</p>
        <p class=" year fw-bold f-sm mb-1 ">{{ item.year }}</p>
  </div>
</template>

<script>
export default {
    name: 'Disc',
    props: ['item']

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