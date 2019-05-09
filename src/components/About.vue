<template>
  <div id="about-container">
    <div class="title">關於我</div>
    <div class="content">
      前端工程師，平常喜歡玩電腦、看電影、寫寫自己的網站、玩貓！(´ω`)
      <br>
      <div class="about-img">
        <img src="../assets/images/play_cat.jpg">
      </div>
      <br>主修 Angular2，對於 React、Vue 也略有涉略
      <br>懂一些後端，主要使用過 Golang 和 Nodejs，也寫過 Java 和 Python
      <br>
      <br>可是其實以前在研究所寫的是 c (遮臉)
      <br>
      <br>我的 Email：
      <a :href="mailTo">miatlab@gmail.com</a>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    mailTo: `mailto:miatlab@gmail.com?subject=${encodeURIComponent(
      'Calico & MooMoo'
    )}`
  })
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
  }
  .content {
    display: inline-block;
    margin-top: 5px;
    padding: 8px 10px;
    font-size: 18px;
    color: #eeeeee;
    background-color: #323232;
    .about-img {
      display: inline-block;
      margin-top: 2px;
      img {
        width: 100%;
      }
    }
    a {
      color: #eeeeee;
    }
  }

  @media only screen and (max-width: 767px) {
    padding: 1vh 0 2vh 0;
    .title {
      font-size: 24px;
    }
    .content {
      font-size: 16px;
    }
  }
}
</style>
