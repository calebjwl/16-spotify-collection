<template lang="html">
  <div class="app">
    <div class="logo">
      <img src="/images/logo.png">
    </div>
    <div class="section page">
      <form class="search" v-on:submit.prevent="searchForTitle(name)">
        <input v-model="name" type="text" class="search-bar" placeholder="Search...">
        <button class="search-submit">Submit</button>
      </form>
      <!-- <div class="panel"> -->
        <div class="results">
          <song-item v-for="item in songs" v-bind:track="item"></song-item>
        </div>
      <!-- </div> -->
    </div>
  </div>
</template>

<script>
import songItem from './song-item.vue';
export default {
  components: {
    songItem,
  },

  data() {
    return {
      songs: []
    };
  },

  methods: {
    searchForTitle(name) {
      fetch(`https://api.spotify.com/v1/search?query=${name}&type=track&offset=0&limit=20`)
        .then(response => response.json())
        .then((trax) => {
          this.songs = trax.tracks.items;
        });
    },
  },
};
</script>
