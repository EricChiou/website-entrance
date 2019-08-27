<template>
  <div class="home">
    <div class="bg">
      <div class="inline-block"></div>
      <img src="../assets/images/bi.jpg" />
      <img class="mobile" src="../assets/images/bi_m.jpg" />
      <div class="mask"></div>
    </div>
    <div class="main">
      <div class="content">
        <Header></Header>
        <Album></Album>
        <div class="show-bg"></div>
        <Entrance></Entrance>
        <div class="show-bg"></div>
        <About></About>
        <Footer></Footer>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '../components/Header.vue';
import Album from '../components/Album.vue';
import Entrance from '../components/Entrance.vue';
import About from '../components/About.vue';
import Footer from '../components/Footer.vue';

export default {
  name: 'home',
  components: {
    Header,
    Album,
    Entrance,
    About,
    Footer
  }
};
</script>

<style lang="scss" scoped>
.home {
  background-color: #212121;
  .bg,
  .main {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
  }
  .bg {
    background-color: #212121;
    .inline-block {
      display: inline-block;
      height: 100%;
      vertical-align: middle;
    }
    img {
      display: inline-block;
      width: 100%;
      max-height: 100%;
      object-fit: contain;
      vertical-align: middle;
    }
    .mobile {
      display: none;
    }
    .mask {
      position: fixed;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      background-color: rgba(0, 0, 0, 0.4);
    }
  }
  .main {
    overflow: auto;
    .content {
      .show-bg {
        height: 30vh;
      }
    }
  }
  @media only screen and (max-width: 767px) {
    .bg {
      img {
        display: none;
      }
      .mobile {
        display: inline-block;
      }
    }
    .main {
      .content {
        margin: 0;
        .show-bg {
          height: 20vh;
        }
      }
    }
  }
}
</style>
