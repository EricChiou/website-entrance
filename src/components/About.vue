<template>
  <div id="about-container">
    <div class="title">
      <div class="text">
        <img src="../assets/images/moomoo_head_tie.png" />
        關於我
      </div>
    </div>
    <div ref="content" class="content">
      <iframe src="https://www.calicomoo.ml/about?color=#eeeeee&fontSize=18px&textAlign=center"></iframe>
    </div>
  </div>
</template>

<script>
import { setTimeout } from 'timers';
export default {
  methods: {
    resize() {
      const iframe = document.getElementsByTagName('iframe')[0];
      if (iframe) {
        const contentDocument = iframe.contentDocument;
        if (contentDocument) {
          const about = contentDocument.getElementById('about');
          if (about) {
            this.$refs.content.style.height = `${about.scrollHeight}px`;
            return;
          }
        }
      }
      setTimeout(() => {
        this.resize();
      }, 100);
    }
  },
  mounted() {
    this.resize();
  }
};
</script>

<style lang="scss" scoped>
#about-container {
  padding: 3vh 0 5vh 0;
  text-align: center;
  color: #eeeeee;
  background-color: #212121;
  .title {
    font-size: 32px;
    font-weight: bold;
    text-align: center;
    text-decoration: underline;
    .text {
      position: relative;
      display: inline-block;
      height: 75px;
      font-size: 32px;
      font-weight: bold;
      text-decoration: underline;
      color: #eeeeee;
      line-height: 75px;
      img {
        position: absolute;
        top: -5px;
        right: calc(100% + 5px);
        bottom: 5px;
        height: 75px;
      }
    }
  }
  .content {
    display: inline-block;
    margin-top: 5px;
    padding: 8px 10px;
    font-size: 18px;
    color: #eeeeee;
    background-color: #323232;
    iframe {
      width: 640px;
      max-width: 100%;
      border: none;
    }
  }

  @media only screen and (max-width: 767px) {
    padding: 1vh 0 2vh 0;
    .title {
      .text {
        font-size: 24px;
        height: 65px;
        line-height: 65px;
        img {
          top: -3px;
          bottom: 3px;
          height: 65px;
        }
      }
    }
    .content {
      font-size: 16px;
    }
  }
}
</style>
