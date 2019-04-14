<template>
  <div id="footer-container">
    <ul>
      <li class="border">
        <a href="mailto:ericexexeric@hotmail.com?subject=由入口網站聯繫">聯絡我</a>
      </li>
      <li>
        <a href="https://github.com/EricChiou/website-entrance" target="_blank">
          <img src="../assets/github.png" width="25" height="25">Github
        </a>
      </li>
    </ul>
    <div class="right">© 2019 All rights reserved</div>
  </div>
</template>

<script>
export default {
  name: 'Footer'
};
</script>

<style lang="scss" scoped>
#footer-container {
  padding: 15px 0;
  text-align: center;
  background-color: #323232;
  ul {
    margin: 0;
    padding: 0;
    li {
      display: inline-block;
      padding: 0 10px;
      list-style: none;
      font-size: 20px;
      font-weight: bold;
      color: #eeeeee;
      cursor: pointer;
      img {
        margin-right: 4px;
        margin-bottom: -4px;
      }
    }
    .border {
      border-right: 2px solid #eeeeee;
    }
  }
  .right {
    margin-top: 5px;
    color: #aaa;
  }
  a {
    color: #eeeeee;
    text-decoration: none;
  }
}
</style>
