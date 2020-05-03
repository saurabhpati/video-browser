<template>
  <div id="app" class="container">
    <SearchBar @termChange="onTermChange" />
    <VideoList :videos="videos"></VideoList>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import axios from "axios";
import SearchBar from "./components/SearchBar.vue";
import VideoList from "./components/VideoList.vue";

const API_KEY = "AIzaSyDHRrpDbA9uEYWKY_hpsZ6H5DvLH-e0OcM";

export default {
  name: "app",
  components: {
    SearchBar,
    VideoList
  },
  data() {
    return {
      videos: []
    };
  },
  methods: {
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(response => {
          this.videos = response.data.items;
        });
    }
  }
};
</script>

<style>

</style>
