<template>
  <div class="entrance-block-container">
    <div class="entrance-block" @click="link2Website(website.url)">
      <div class="entrance-content">
        <img :src="website.imgSrc" />
        <div ref="icon" class="icon"></div>
        <div class="website-title">{{website.title}}</div>
        <div class="website-description">
          <div class="inline-block"></div>
          <div class="content">{{website.content}}</div>
          <div class="short-content">{{website.shortContent}}</div>
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
      url: String,
      imgSrc: String,
      title: String,
      content: String,
      shortContent: String,
      icon: String
    }
  },
  methods: {
    link2Website(url) {
      window.location = url;
    }
  },
  mounted() {
    if (this.website.icon) {
      this.$refs.icon.innerHTML = this.website.icon;
      this.$refs.icon.getElementsByTagName('svg')[0].style.width =
        'calc(100% / 3)';
      this.$refs.icon.getElementsByTagName('svg')[0].style.color =
        'rgba(0, 0, 0, 0.7)';
      if (window.innerWidth > 767) {
        this.$refs.icon.getElementsByTagName('svg')[0].style.height = 'auto';
      } else {
        this.$refs.icon.getElementsByTagName('svg')[0].style.height = '100%';
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.entrance-block-container {
  display: inline-block;
  margin: 2.5px 5px;
  width: calc(25% - 10px);
  max-width: 420px;
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
        height: calc(100% * 2 / 3);
        background-color: #ccc;
      }
      .icon {
        position: absolute;
        top: calc(100% * 4 / 9);
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
          text-align: left;
        }
        .short-content {
          display: none;
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
    width: calc(100% / 3 - 10px);
  }
  @media only screen and (max-width: 1023px) {
    width: calc(50% - 10px);
  }
  @media only screen and (max-width: 767px) {
    width: calc(100% - 10px);
    .entrance-block {
      padding-top: 25%;
      .entrance-content {
        text-align: left;
        img {
          display: inline-block;
          width: 25%;
          height: 100%;
          vertical-align: middle;
        }
        .icon {
          top: calc(100% * 2 / 3);
          right: 75%;
          bottom: 0;
          left: 0;
        }
        .website-title {
          position: absolute;
          top: 0;
          right: 0;
          width: calc(75% - 10px);
        }
        .website-description {
          display: inline-block;
          margin: 5px 10px;
          width: calc(75% - 30px);
          height: calc(100% - 30px);
          vertical-align: bottom;
          .content {
            display: none;
          }
          .short-content {
            display: inline-block;
            vertical-align: middle;
            text-align: left;
          }
        }
        .mask {
          display: none;
          &:hover {
            .mask {
              display: none;
            }
          }
        }
      }
    }
  }
}
</style>
