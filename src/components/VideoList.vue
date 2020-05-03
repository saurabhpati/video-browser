<template>
  <ul class="list-group col-md-4">
    <VideoListItem
      @videoSelect="onVideoSelect"
      v-for="video in videos"
      :key="video.id.videoId"
      v-bind:video="video">
    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue';

export default {
  name: 'VideoList',
  components: {
    VideoListItem,
  },
  props: {
    videos: Array
  },
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    }
  }
};
</script>

<style>
</style>