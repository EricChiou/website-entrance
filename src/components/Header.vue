<template>
  <div id="header-container">
    <div class="title">
      <img src="../assets/images/calico_head.png" />
      <div class="text">Calico & MooMoo</div>
      <img src="../assets/images/moomoo_head.png" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style lang="scss" scoped>
#header-container {
  background-color: #454545;

  .title {
    text-align: center;
    .text,
    img {
      display: inline-block;
      vertical-align: middle;
    }

    .text {
      margin: 0 15px;
      font-size: 60px;
      font-weight: bold;
      font-family: monospace;
      color: #eeeeee;

      @media only screen and (max-width: 1024px) {
        font-size: 50px;
      }

      @media only screen and (max-width: 767px) {
        font-size: 30px;
      }

      @media only screen and (max-width: 480px) {
        font-size: 22px;
      }
    }

    img {
      margin: 15px 5px;
      height: 120px;

      @media only screen and (max-width: 1024px) {
        margin: 10px 5px;
        height: 100px;
      }

      @media only screen and (max-width: 767px) {
        margin: 5px;
        height: 65px;
      }

      @media only screen and (max-width: 480px) {
        height: 40px;
      }
    }
  }
}
</style>
