<template>
  <div id="entrance-container">
    <div class="title">
      <div class="text">
        網站入口
        <img src="../assets/images/calico_head_tie.png" />
      </div>
    </div>
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
          '該來的終於還是來啦！\n我的婚禮將於 2019/11/23 舉辦，歡迎大家來參加喔～\n這是電子喜帖的連結。',
        icon: null
      },
      {
        path: 'frontend-daily-life',
        imgSrc: require('../assets/images/frontend_daily_life.png'),
        title: 'Frontend Daily Life',
        content:
          '記錄我在前端遇到的大小事、心得及其他相關技術，並推薦一些好用網站。',
        icon: `
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="currentColor"
          >
            <path d="M0 0h24v24H0z" fill="none" />
            <path d="M18 2H6c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zM6 4h5v8l-2.5-1.5L6 12V4z" />
          </svg>
        `
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
    text-align: center;
    background-color: #212121;
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
        top: 0;
        bottom: 0;
        left: calc(100% + 5px);
        height: 75px;
      }
    }
  }
  .entrance-list {
    margin: 5px 10%;
    padding: 0 10px 10px 10px;
  }
  @media only screen and (max-width: 767px) {
    padding: 1vh 0 2vh 0;
    .title {
      .text {
        font-size: 24px;
        height: 65px;
        line-height: 65px;
        img {
          height: 65px;
        }
      }
    }
    .entrance-list {
      margin: 5px 0;
      padding: 0 5px 10px 5px;
    }
  }
}
</style>
