<template>
  <div class="filter-image">
    <p>{{filter.name}}</p>
    <div class="img"
      :class="filter.name"
      :style="{ backgroundImage: 'url(' + image + ')' }"
      @click="selectFilter"
    />
  </div>
</template>

<script>
import EventBus from '../event-bus';

export default {
  name: 'FilterImage',
  props: {
    filter: Object,
    image: String,
  },
  methods: {
    selectFilter() {
      EventBus.$emit(
        'filter-selected', { filter: this.filter.name },
      );
    },
  },
};
</script>

<style lang="scss" src="../styles/filter-image.scss">
// Styles from stylesheet
</style>
