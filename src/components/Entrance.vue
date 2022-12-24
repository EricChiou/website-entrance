<template>
  <div id="entrance-container">
    <div class="title">
      <div class="text">
        網站入口
        <img src="../assets/images/calico_head_tie.png" />
      </div>
    </div>
    <div class="entrance-list">
      <EntranceBlock
        v-for="website in websites"
        :key="website.link"
        :website="website"
      ></EntranceBlock>
    </div>
  </div>
</template>

<script>
/* eslint-disable no-tabs */
import EntranceBlock from './EntranceBlock.vue';

export default {
  name: 'Entrance',
  components: { EntranceBlock },
  data: () => ({
    websites: [
      {
        url: 'https://www.calicomoomoo.com/wedding',
        imgSrc: require('../assets/images/invitation_card.png'),
        title: 'Wedding Invitation Card',
        content:
          '該來的終於還是來啦！我們的婚禮將於 2019/11/23 舉辦，歡迎大家來參加喔～\n這是電子喜帖的連結。',
        shortContent: '我們婚禮將於 2019/11/23 舉辦，歡迎大家來參加喔～',
        icon: null,
      },
      {
        url: 'https://www.calicomoomoo.com/frontend-daily-life',
        imgSrc: require('../assets/images/moomoo_head.png'),
        title: 'Frontend Daily Life',
        content: '記錄我在前端遇到的大小事、心得及其他相關技術，並推薦一些好用網站。',
        shortContent: '記錄我在前端遇到的大小事、心得及其他相關技術。',
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
        `,
      },
      {
        url: 'https://www.calicomoomoo.com/javascript-components',
        imgSrc: require('../assets/images/moomoo_head.png'),
        title: 'Javascript Components',
        content:
          '各種用純 Javascript, HTML, CSS 製作的元件，例如 Image Editor, Custom Scroll Bar, SHA-3 加密, ...等等。',
        shortContent: '各種用純 Javascript, HTML, CSS 製作的元件。',
        icon: `
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor">
            <path d="M480 288v-64h-34.7c-2-12.1-5.2-23.8-9.3-35l30-17.3-32-55.4-30 17.3c-7.7-9.3-16.3-17.9-25.6-25.6l17.3-30-55.4-32L323 76c-11.2-4.2-22.9-7.3-35-9.3V32h-64v34.7c-12.1 2-23.8 5.2-35 9.3l-17.3-30-55.4 32 17.3 30c-9.3 7.7-17.9 16.3-25.6 25.6l-30-17.3-32 55.4L76 189c-4.2 11.2-7.3 22.9-9.3 35H32v64h34.7c2 12.1 5.2 23.8 9.3 35l-30 17.3 32 55.4 30-17.3c7.7 9.3 16.3 17.9 25.6 25.6l-17.3 30 55.4 32 17.3-30c11.2 4.2 22.9 7.3 35 9.3V480h64v-34.7c12.1-2 23.8-5.2 35-9.3l17.3 30 55.4-32-17.3-30c9.3-7.7 17.9-16.3 25.6-25.6l30 17.3 32-55.4-30-17.3c4.2-11.2 7.3-22.9 9.3-35H480zm-224-64c17.7 0 32 14.3 32 32s-14.3 32-32 32-32-14.3-32-32 14.3-32 32-32zM141.2 343c-18.3-24.2-29.2-54.3-29.2-87 0-6.1.4-12.1 1.1-18l46.9 17.1v.9c0 17.8 4.9 34.5 13.3 48.8L141.2 343zm40.7-148L135 177.9c20.1-31.1 51.8-53.9 89-62.3v49.9c-16.6 5.9-31.1 16.2-42.1 29.5zM256 400c-23.7 0-46-5.7-65.8-15.9l32.1-38.2c10.5 3.9 21.8 6.1 33.7 6.1s23.2-2.2 33.7-6.1l32.1 38.2C302 394.3 279.7 400 256 400zm32-234.5v-49.9c37.2 8.4 68.9 31.2 89 62.3L330.1 195c-11-13.3-25.5-23.6-42.1-29.5zM370.8 343l-32.1-38.2c8.4-14.3 13.3-31 13.3-48.8v-.9l46.9-17.1c.7 5.9 1.1 11.9 1.1 18 0 32.7-10.9 62.8-29.2 87z"/>
          </svg>
        `,
      },
      {
        url: 'https://www.calicomoomoo.com/yt-player',
        imgSrc: require('../assets/images/calico_head.png'),
        title: 'YT Player',
        content:
          '可以搜尋 Youtube 影片並將你想看的影片加入播放列表，或是直接輸入 Video ID 加入播放列表。',
        shortContent: '可以搜尋 Youtube 影片並加入播放列表。',
        icon: `
          <svg enable-background="new 0 0 512 512" id="Layer_1" version="1.1" viewBox="0 0 512 512" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g>
              <path fill="currentColor" d="M260.4,449c-57.1-1.8-111.4-3.2-165.7-5.3c-11.7-0.5-23.6-2.3-35-5c-21.4-5-36.2-17.9-43.8-39c-6.1-17-8.3-34.5-9.9-52.3 C2.5,305.6,2.5,263.8,4.2,222c1-23.6,1.6-47.4,7.9-70.3c3.8-13.7,8.4-27.1,19.5-37c11.7-10.5,25.4-16.8,41-17.5 c42.8-2.1,85.5-4.7,128.3-5.1c57.6-0.6,115.3,0.2,172.9,1.3c24.9,0.5,50,1.8,74.7,5c22.6,3,39.5,15.6,48.5,37.6 c6.9,16.9,9.5,34.6,11,52.6c3.9,45.1,4,90.2,1.8,135.3c-1.1,22.9-2.2,45.9-8.7,68.2c-7.4,25.6-23.1,42.5-49.3,48.3 c-10.2,2.2-20.8,3-31.2,3.4C366.2,445.7,311.9,447.4,260.4,449z M205.1,335.3c45.6-23.6,90.7-47,136.7-70.9 c-45.9-24-91-47.5-136.7-71.4C205.1,240.7,205.1,287.6,205.1,335.3z"/>
            </g>
          </svg>
        `,
      },
      {
        url: 'https://www.calicomoomoo.com/otter-cloud',
        imgSrc: require('../assets/images/calico_head.png'),
        title: 'Otter Cloud',
        content: 'Calico & MooMoo Otter 雲端硬碟。',
        shortContent: 'Calico & MooMoo 雲端硬碟。',
        icon: `
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path d="M0 0h24v24H0z" fill="none"/>
            <path fill="currentColor" d="M19.35 10.04C18.67 6.59 15.64 4 12 4 9.11 4 6.6 5.64 5.35 8.04 2.34 8.36 0 10.91 0 14c0 3.31 2.69 6 6 6h13c2.76 0 5-2.24 5-5 0-2.64-2.05-4.78-4.65-4.96zM14 13v4h-4v-4H7l5-5 5 5h-3z"/>
          </svg>
        `,
      },
      {
        url: 'https://www.calicomoomoo.com/minecraft',
        imgSrc: require('../assets/images/moomoo_head.png'),
        title: 'Minecarft Server',
        content: 'Calico & MooMoo Minecraft Server。',
        shortContent: 'Calico & MooMoo Minecraft Server。',
        icon: `
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" id="Layer_1" x="0px" y="0px" width="864px" height="864px" viewBox="0 0 864 864" enable-background="new 0 0 864 864" xml:space="preserve">
            <g>
	            <path fill="currentColor" fill-rule="evenodd" clip-rule="evenodd" d="M758.567,113.176c0,215.327,0,429.207,0,644.506c-215.215,0-429.912,0-645.704,0 c0-214.5,0-428.795,0-644.506C327.478,113.176,542.173,113.176,758.567,113.176z"/>
	            <path fill-rule="evenodd" clip-rule="evenodd" fill="rgba(255, 255 ,255, 0.7)" d="M137.333,137.323c0,198.884,0,395.854,0,593.83 c199.175,0,397.201,0,596.219,0c0.39-6.018,1-595.143,1-595.143C548.199,136.573,143.562,137.019,137.333,137.323z M207.491,256.627c11.139,0,150.251,2.444,150.251,2.444c0.886,38.729-0.159,83.679-0.159,124.007c-51.779,0-100.228,0-150.093,0 C207.491,341.278,207.491,300.36,207.491,256.627z M588.743,644.729c0,0-69.767-0.163-73.901-0.024 c-0.03,0.01-0.06,0.026-0.092,0.024c-0.171-0.009-0.127-0.018,0.092-0.024c3.228-1.077-0.593-67.855-0.593-67.855 c-25.848,0-134.963,0.29-156.151-0.305v66.323c0,0-51.736,0.117-74.172,0.117c0-65.145,0-127.409,0-192.044 c25.198,0,49.589,0,75.714,0c0-22.062,0-41.81,0-62.909c51.201,0,100.611,0,151.543,0c0,19.861,0,39.129,0,60.06 c26.336,0,51.249,0,77.56,0C588.743,514.078,588.743,578.39,588.743,644.729z M666.555,383.386c-50.694,0-100.421,0-151.805,0 c0-41.935,0-83.841,0-126.823c50.092,0,99.761,0,151.805,0C666.555,299.078,666.555,340.618,666.555,383.386z"/>
            </g>
          </svg>
        `,
      },
      {
        url: 'https://www.calicomoomoo.com/otter-calendar',
        imgSrc: require('../assets/images/otter_calendar.png'),
        title: 'Otter Calendar',
        content: '可以記錄事件最後執行時間並且顯示下次執行時間。',
        shortContent: '記錄事件最後執行時間並顯示下次執行時間。',
        icon: '',
      },
    ],
  }),
};
</script>

<style lang="scss" scoped>
#entrance-container {
  padding: 10vh 0 16vh 0;
  background-color: rgba(0, 0, 0, 0.25);
  .title {
    text-align: center;
    .text {
      position: relative;
      display: inline-block;
      height: 75px;
      font-size: 32px;
      font-weight: bold;
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
    text-align: center;
  }
  @media only screen and (max-width: 767px) {
    padding: 5vh 0 8vh 0;
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
