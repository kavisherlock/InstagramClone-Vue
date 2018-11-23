<template>
  <div id='app'>
    <div class="app-phone">
      <div class="phone-header">
        <img src="./images/logo.png" />
      </div>
      <phone-body
        :posts="posts"
        :filters="filters"
      />
      <div class="phone-footer">
        <div class="home-cta">
          <i class="fas fa-home fa-lg" />
        </div>
        <div class="upload-cta">
          <i class="far fa-plus-square fa-lg" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Body from './components/Body';
import posts from './data/posts';
import filters from './data/filters';

export default {
  name: 'App',
  data() {
    return {
      posts,
      filters,
    };
  },
  components: {
    'phone-body': Body,
  },
};
</script>

<style lang='scss' src='./styles/app.scss'>
// Styles from stylesheet
</style>
