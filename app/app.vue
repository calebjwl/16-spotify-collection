<template lang="html">
  <div class="app">
    <div class="section page">
      <div class="panel">
        <div class="results">
          <song-item v-for="item in songs" v-bind:track="item"></song-item>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import songItem from './song-item.vue';
export default {
  components: {
    songItem,
  },

  created() {
    fetch('https://api.spotify.com/v1/search?query=chance&type=track&offset=0&limit=20')
      .then(response => response.json())
      .then((trax) => {
        this.songs = trax.tracks.items;
      });
  },

  data() {
    return {
      songs: [{
        artist: [{
          name: 'CHANCE',
        }],
        name: 'Favorite Song',
      }]
    };
  },

  methods: {

  },
};
</script>
