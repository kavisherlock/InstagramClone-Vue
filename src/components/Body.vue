<template>
  <div class="phone-body">
    <div v-if="step === 1" class="feed">
      <instagram-post v-for="post in posts"
        :post="post"
        :key="posts.indexOf(post)"
      />
    </div>
    <div v-if="step === 2" class="image-upload">
      <div class="selected-image"
        :class="selectedFilter"
        :style="{ backgroundImage: 'url(' + image + ')' }"
      />
      <div class="filter-container">
        <filter-image v-for="filter in filters"
          :filter="filter"
          :image="image"
          :key="filters.indexOf(filter)">
        </filter-image>
      </div>
    </div>
  </div>
</template>

<script>
import InstagramPost from './InstagramPost';
import FilterImage from './FilterImage';

export default {
  name: 'Body',
  props: {
    posts: Array,
    filters: Array,
    step: Number,
    image: String,
    selectedFilter: String,
  },
  components: {
    'instagram-post': InstagramPost,
    'filter-image': FilterImage,
  },
};
</script>

<style lang="scss" src="../styles/phone-body.scss">
// Styles from stylesheet
</style>
