<template>
  <div class="instagram-post">
    <div class="header level">
        <div class="level-left">
          <figure class="image is-32x32">
            <img :src="post.userImage" />
          </figure>
          <span class="username">{{post.username}}</span>
        </div>
    </div>
    <div class="image-container"
      :class="post.filter"
      :style="{ backgroundImage: 'url(' + post.postImage + ')' }"
    />
    <div class="content">
      <div class="heart">
        <i class="far fa-heart fa-lg" />
        <span class="likes">{{post.likes}} likes</span>
      </div>
      <p class="caption">
        <span class="username">{{post.username}}</span>{{post.caption}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'InstagramPost',
  props: {
    post: Object,
  },
};
</script>

<style lang="scss" src="../styles/instagram-post.scss">
// Styles from stylesheet
</style>
