<template>
  <div id="entrance-container">
    <div class="title">網站入口</div>
    <div class="entrance-list">
      <div class="entrance-block" @click="link2Website('wedding')">
        <img src="../assets/images/invitation_card.png">
        <div class="website-title">Wedding Invitation Card</div>
        <div class="website-description">
          <div class="inline-block"></div>
          <div class="content">
            該來的終於還是來啦！
            <br>我的婚禮將於 2019/11/23 舉辦，歡迎大家來參加喔～
            <br>這是電子喜帖的連結
          </div>
        </div>
        <div class="mask">
          <div class="inline-block"></div>
          <div class="go">前往網站</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Entrance',
  methods: {
    link2Website: url => {
      console.log(window.location.origin + '/' + url);
      window.location = window.location.origin + '/' + url;
    }
  }
};
</script>

<style lang="scss" scoped>
#entrance-container {
  padding: 3vh 0 5vh 0;
  background-color: #212121;
  .title {
    font-size: 32px;
    font-weight: bold;
    text-align: center;
    text-decoration: underline;
    color: #eeeeee;
    background-color: #212121;
  }
  .entrance-list {
    margin: 5px 10%;
    padding: 0 10px 10px 10px;
    .entrance-block {
      display: inline-block;
      position: relative;
      width: calc(25% - 10px);
      margin: 0 5px;
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
    }
  }
  .inline-block {
    display: inline-block;
    height: 100%;
    vertical-align: middle;
  }
  @media only screen and (max-width: 767px) {
    padding: 1vh 0 2vh 0;
    .title {
      font-size: 24px;
    }
    .entrance-list {
      margin: 5px 0;
      padding: 0 5px 10px 5px;
      .entrance-block {
        width: calc(100% - 10px);
        margin: 2.5px 5px;
      }
    }
  }
}
</style>
