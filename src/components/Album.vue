<template>
  <div id="album-container">
    <div class="album">
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
  </div>
</template>

<script>
export default {
  name: 'Album'
};
</script>

<style lang="scss" scoped>
#album-container {
  background-color: #212121;
  .album {
    padding: 3vh 0 5vh 0;
    .title {
      font-size: 32px;
      font-weight: bold;
      font-family: monospace;
      text-align: center;
      text-decoration: underline;
      color: #eeeeee;
    }
    .picture-list {
      margin: 5px 10%;
      padding: 15px 10px 10px 10px;
      text-align: center;
      background-color: #323232;
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
  }
  @media only screen and (max-width: 767px) {
    .album {
      padding: 1vh 0 2vh 0;
      .title {
        font-size: 24px;
      }
      .picture-list {
        margin: 5px 0;
        padding: 15px 5px 10px 5px;
        .picture {
          width: calc(50% - 10px);
          margin: 2.5px 5px;
        }
      }
    }
  }
}
</style>
