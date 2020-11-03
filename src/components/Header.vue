<template>
  <div id="header-container">
    <div class="background-img">
      <img class="header-bi" src="../assets/images/header_bi.png">
      <img class="header-bi-m" src="../assets/images/header_bi_m.png">
      <img class="title" src="../assets/images/header_title.png">
      <!-- <img class="sub-title" src="../assets/images/header_sub_title.png"> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
};
</script>

<style lang="scss" scoped>
#header-container {
  position: relative;
  .header-bi,
  .header-bi-m {
    width: 100%;
  }
  .header-bi {
    display: block;
  }
  .header-bi-m {
    display: none;
  }
  .title {
    position: absolute;
    top: 10%;
    left: 19%;
    height: 70%;
  }
  .sub-title {
    position: absolute;
    top: 45%;
    left: 35%;
    height: 50%;
  }
  @media only screen and (max-width: 767px) {
    .header-bi {
      display: none;
    }
    .header-bi-m {
      display: block;
    }
    .title {
      left: 25%;
      transform: scale(0.8);
    }
    .sub-title {
      left: 55%;
    }
  }
}
</style>
