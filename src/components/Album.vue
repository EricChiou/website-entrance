<template>
  <div id="album-container">
    <div class="album">
      <div class="title">
        <img src="../assets/images/calico_head.png" />
        <div class="text">Calico & MooMoo</div>
        <img src="../assets/images/moomoo_head.png" />
      </div>
      <div class="picture-list">
        <div class="picture">
          <img src="../assets/images/calico_1.png" />
        </div>
        <div class="picture">
          <img src="../assets/images/calico_2.jpg" />
        </div>
        <div class="picture">
          <img src="../assets/images/moomoo_1.jpg" />
        </div>
        <div class="picture">
          <img src="../assets/images/moomoo_2.png" />
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
      text-align: center;
      .text,
      img {
        display: inline-block;
        vertical-align: middle;
      }
      .text {
        margin: 0 10px 0 5px;
        font-size: 32px;
        font-weight: bold;
        font-family: monospace;
        color: #eeeeee;
      }
      img {
        height: 85px;
      }
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
        white-space: nowrap;
        .text {
          font-size: 24px;
        }
        img {
          height: 60px;
        }
        @media only screen and (max-width: 359px) {
          .text {
            font-size: 22px;
          }
          img {
            height: 55px;
          }
        }
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
