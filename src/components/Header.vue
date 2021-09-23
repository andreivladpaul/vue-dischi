<template>
  <div class="header px-3 py-2 d-flex justify-content-between">
      <img src="../assets/spotify-logo.png" alt="">

      <div class="search d-flex justify-content-center align-items-center"  >
          <input type="text" class="px-1 me-2 rounded-1"  placeholder="Search by genre">
          <button type="input" class="px-3 py-1 me-2 rounded-1">Search</button>

      </div>
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
        .search {
            input {
                
                &::placeholder {
                    font-size: 16px;
                }
           
            }
             button {
                    background-color: rgb(10, 180, 101);
                    color: #fff;
                    border: none;
                    font-size: 16px;
            }
        }


        
    }

</style>