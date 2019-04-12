<template>
  <div id="album-container">
    <div class="title">Calico & MooMoo</div>
    <div class="picture-list">
      <div class="picture">
        <img src="../assets/calico_1.jpg">
      </div>
      <div class="picture">
        <img src="../assets/calico_2.jpg">
      </div>
      <div class="picture">
        <img src="../assets/moomoo_1.jpg">
      </div>
      <div class="picture">
        <img src="../assets/moomoo_2.jpg">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Album'
};
</script>

<style lang="scss" scoped>
#album-container {
  padding: 10px 0;
  background-color: #222831;
  .title {
    font-size: 32px;
    font-weight: bold;
    font-family: monospace;
    text-align: center;
    color: #eeeeee;
  }
  .picture-list {
    margin: 5px 10%;
    padding: 15px 10px 10px 10px;
    text-align: center;
    background-color: #393e46;
    .picture {
      display: inline-block;
      width: calc(25% - 10px);
      margin: 0 5px;
      img {
        display: inline-block;
        width: 100%;
      }
    }
  }
  @media only screen and (max-width: 767px) {
    padding: 5px 0;
    .title {
      padding: 0;
      font-size: 24px;
    }
    .picture-list {
      margin: 5px 0;
      padding: 15px 5px 10px 5px;
      .picture {
        margin: 2.5px 5px;
        width: calc(50% - 10px);
      }
    }
  }
}
</style>


