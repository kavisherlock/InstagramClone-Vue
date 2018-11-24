<template>
  <div class="phone-body">
    <div v-if="step === 1" class="feed" v-dragscroll.y>
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
      <div class="filter-container" v-dragscroll.x>
        <filter-image v-for="filter in filters"
          :filter="filter"
          :image="image"
          :key="filters.indexOf(filter)">
        </filter-image>
      </div>
    </div>

    <div v-if="step === 3" class="image-upload">
      <div class="selected-image"
        :class="selectedFilter"
        :style="{ backgroundImage: 'url(' + image + ')' }">
      </div>
      <div class="caption-container">
        <textarea class="caption-input"
          placeholder="Enter a caption..."
          type="text"
          :value="value"
          @input="$emit('input', $event.target.value)"
        />
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
    value: String,
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
