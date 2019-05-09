<template>
  <div class="entrance-block-container">
    <div class="entrance-block" @click="link2Website(website.path)">
      <img :src="website.imgSrc">
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
</template>

<script>
export default {
  props: {
    website: { path: String, imgSrc: String, title: String, content: String }
  },
  methods: {
    link2Website(path) {
      window.location = window.location.origin + '/' + path;
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
    color: #323232;
    background-color: #eeeeee;
    cursor: pointer;
    &:hover {
      .mask {
        display: block;
      }
    }
    img {
      width: 100%;
    }
    .website-title {
      margin: 5px;
      font-size: 20px;
      font-weight: bold;
      text-align: center;
      text-decoration: underline;
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
    .inline-block {
      display: inline-block;
      height: 100%;
      vertical-align: middle;
    }
  }
  @media only screen and (max-width: 767px) {
    margin: 2.5px 5px;
    width: calc(100% - 10px);
  }
}
</style>
