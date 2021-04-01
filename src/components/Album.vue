<template>
  <div id="album-container">
    <div class="album">
      <!-- <div class="title">
        <img src="../assets/images/calico_head.png" />
        <div class="text">Calico & MooMoo</div>
        <img src="../assets/images/moomoo_head.png" />
      </div> -->
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
  name: 'Album',
};
</script>

<style lang="scss" scoped>
#album-container {
  background-color: #212121;
  .album {
    padding: calc(3vh + 5px) 0 3vh 0;

    .picture-list {
      margin: 0 10vw;
      text-align: center;

      .picture {
        display: inline-block;
        width: calc(25% - 10px);
        margin: 0 5px;

        img {
          display: block;
          width: 100%;
        }
      }
    }
  }
  @media only screen and (max-width: 767px) {
    .album {
      padding: calc(2vh + 4px) 0 2vh 0;
      height: auto;

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
        margin: 0;
        padding: 0 7px;

        .picture {
          width: calc(50% - 6px);
          margin: 1.5px 3px;
        }
      }
    }
  }
}
</style>
