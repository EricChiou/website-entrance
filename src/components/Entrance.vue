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
        imgSrc: require('../assets/images/moomoo_head.png'),
        title: 'Frontend Daily Life',
        content:
          '記錄我在前端遇到的大小事、心得及其他相關技術，並推薦一些好用網站。',
        icon: `
          <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 64 64" enable-background="new 0 0 64 64" xml:space="preserve" fill="currentColor">
            <g id="BOOK_1_" enable-background="new">
              <g id="BOOK">
                <g>
                  <path d="M10,18h8c1.657,0,3-1.343,3-3s-1.343-3-3-3h-8c-1.657,0-3,1.343-3,3S8.343,18,10,18z M10,35h8c1.657,0,3-1.343,3-3 s-1.343-3-3-3h-8c-1.657,0-3,1.343-3,3S8.343,35,10,35z M54,3h-3v58h3c1.657,0,3-1.343,3-3V6C57,4.343,55.657,3,54,3z M13,6v3h5 c3.314,0,6,2.686,6,6s-2.686,6-6,6h-5v5h5c3.314,0,6,2.686,6,6c0,3.314-2.686,6-6,6h-5v5h5c3.314,0,6,2.686,6,6s-2.686,6-6,6h-5 v3c0,1.657,1.343,3,3,3h32V3H16C14.343,3,13,4.343,13,6z M21,49c0-1.657-1.343-3-3-3h-8c-1.657,0-3,1.343-3,3s1.343,3,3,3h8 C19.657,52,21,50.657,21,49z"/>
                </g>
              </g>
            </g>
          </svg>
        `
      },
      {
        path: 'javascript-components',
        imgSrc: require('../assets/images/moomoo_head.png'),
        title: 'Javascript Components',
        content:
          '各種用純 Javascript, HTML, CSS 製作的元件，例如 Image Editor, Custom Scroll Bar, SHA-3 加密, ...等等。',
        icon: `
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor">
            <path d="M480 288v-64h-34.7c-2-12.1-5.2-23.8-9.3-35l30-17.3-32-55.4-30 17.3c-7.7-9.3-16.3-17.9-25.6-25.6l17.3-30-55.4-32L323 76c-11.2-4.2-22.9-7.3-35-9.3V32h-64v34.7c-12.1 2-23.8 5.2-35 9.3l-17.3-30-55.4 32 17.3 30c-9.3 7.7-17.9 16.3-25.6 25.6l-30-17.3-32 55.4L76 189c-4.2 11.2-7.3 22.9-9.3 35H32v64h34.7c2 12.1 5.2 23.8 9.3 35l-30 17.3 32 55.4 30-17.3c7.7 9.3 16.3 17.9 25.6 25.6l-17.3 30 55.4 32 17.3-30c11.2 4.2 22.9 7.3 35 9.3V480h64v-34.7c12.1-2 23.8-5.2 35-9.3l17.3 30 55.4-32-17.3-30c9.3-7.7 17.9-16.3 25.6-25.6l30 17.3 32-55.4-30-17.3c4.2-11.2 7.3-22.9 9.3-35H480zm-224-64c17.7 0 32 14.3 32 32s-14.3 32-32 32-32-14.3-32-32 14.3-32 32-32zM141.2 343c-18.3-24.2-29.2-54.3-29.2-87 0-6.1.4-12.1 1.1-18l46.9 17.1v.9c0 17.8 4.9 34.5 13.3 48.8L141.2 343zm40.7-148L135 177.9c20.1-31.1 51.8-53.9 89-62.3v49.9c-16.6 5.9-31.1 16.2-42.1 29.5zM256 400c-23.7 0-46-5.7-65.8-15.9l32.1-38.2c10.5 3.9 21.8 6.1 33.7 6.1s23.2-2.2 33.7-6.1l32.1 38.2C302 394.3 279.7 400 256 400zm32-234.5v-49.9c37.2 8.4 68.9 31.2 89 62.3L330.1 195c-11-13.3-25.5-23.6-42.1-29.5zM370.8 343l-32.1-38.2c8.4-14.3 13.3-31 13.3-48.8v-.9l46.9-17.1c.7 5.9 1.1 11.9 1.1 18 0 32.7-10.9 62.8-29.2 87z"/>
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
      text-align: center;
    }
  }
}
</style>
