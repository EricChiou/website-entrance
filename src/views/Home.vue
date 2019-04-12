<template>
  <div class="home">
    <Header></Header>
    <Album></Album>
  </div>
</template>

<script>
import Header from '../components/Header.vue';
import Album from '../components/Album.vue';

export default {
  name: 'home',
  components: {
    Header,
    Album
  }
};
</script>
