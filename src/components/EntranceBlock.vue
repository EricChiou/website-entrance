<template>
  <div class="entrance-block-container">
    <div class="entrance-block" @click="link2Website(website.path)">
      <div class="entrance-content">
        <img :src="website.imgSrc" />
        <div ref="icon" class="icon"></div>
        <div class="website-title">{{website.title}}</div>
        <div class="website-description">
          <div class="inline-block"></div>
          <div class="content">{{website.content}}</div>
        </div>
        <div class="mask">
          <div class="inline-block"></div>
          <div class="go">前往</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    website: {
      path: String,
      imgSrc: String,
      title: String,
      content: String,
      icon: String
    }
  },
  methods: {
    link2Website(path) {
      window.location = window.location.origin + '/' + path;
    }
  },
  mounted() {
    if (this.website.icon) {
      this.$refs.icon.innerHTML = this.website.icon;
      this.$refs.icon.getElementsByTagName('svg')[0].style.width = '30%';
      this.$refs.icon.getElementsByTagName('svg')[0].style.height = 'auto';
      this.$refs.icon.getElementsByTagName('svg')[0].style.color = 'rgba(0, 0, 0, 0.7)';
    }
  }
};
</script>

<style lang="scss" scoped>
.entrance-block-container {
  display: inline-block;
  margin: 0 5px;
  width: calc(25% - 10px);
  .entrance-block {
    position: relative;
    padding-top: 150%;
    color: #323232;
    background-color: #eeeeee;
    cursor: pointer;
    .entrance-content {
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      img {
        width: 100%;
        background-color: #ccc;
      }
      .icon {
        position: absolute;
        top: 47.5%;
        right: 0;
        left: 0;
        text-align: right;
      }
      .website-title {
        margin: 5px;
        font-size: 20px;
        font-weight: bold;
        text-align: center;
        text-decoration: underline;
        @media only screen and (max-width: 1200px) {
          font-size: 18px;
        }
      }
      .website-description {
        margin: 5px 15px;
        height: 100px;
        .content {
          display: inline-block;
          vertical-align: middle;
        }
      }
      .mask {
        display: none;
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        font-size: 64px;
        font-weight: bold;
        text-align: center;
        color: #eeeeee;
        background-color: rgba(0, 0, 0, 0.4);
        .go {
          display: inline-block;
          vertical-align: middle;
        }
      }
      &:hover {
        .mask {
          display: block;
        }
      }
      .inline-block {
        display: inline-block;
        height: 100%;
        vertical-align: middle;
      }
    }
  }
  @media only screen and (max-width: 1399px) {
    margin: 2.5px 5px;
    width: calc(100% / 3 - 10px);
  }
  @media only screen and (max-width: 1023px) {
    margin: 2.5px 5px;
    width: calc(50% - 10px);
  }
  @media only screen and (max-width: 767px) {
    margin: 2.5px 5px;
    width: calc(100% - 10px);
  }
}
</style>
