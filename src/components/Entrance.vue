<template>
  <div id="entrance-container">
    <div class="title">網站入口</div>
    <div class="entrance-list">
      <EntranceBlock v-for="website in websites" :key="website.link" :website="website"></EntranceBlock>
    </div>
  </div>
</template>

<script>
import EntranceBlock from './EntranceBlock.vue';

export default {
  name: 'Entrance',
  components: { EntranceBlock },
  data: () => ({
    websites: [
      {
        path: 'wedding',
        imgSrc: require('../assets/images/invitation_card.png'),
        title: 'Wedding Invitation Card',
        content:
          '該來的終於還是來啦！\n我的婚禮將於 2019/11/23 舉辦，歡迎大家來參加喔～\n這是電子喜帖的連結'
      },
      {
        path: 'frontend-daily-life',
        imgSrc: require('../assets/images/frontend_daily_life.png'),
        title: 'Frontend Daily Life',
        content:
          '記錄我在前端遇到的大小事、心得及其他相關技術，並推薦一些好用網站。'
      }
    ]
  }),
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
  }
  @media only screen and (max-width: 767px) {
    padding: 1vh 0 2vh 0;
    .title {
      font-size: 24px;
    }
    .entrance-list {
      margin: 5px 0;
      padding: 0 5px 10px 5px;
    }
  }
}
</style>
