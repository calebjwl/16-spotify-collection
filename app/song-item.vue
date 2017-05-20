<template lang="html">
  <a v-bind:href="track.external_urls.spotify">
    <div class="song-item">
      <div class="track">
        <div class="panel-block media">
          <div class="media-left">
            <img v-bind:src="track.album.images[0].url" alt="" class="track__frame track__media">
          </div>

          <div class="media-content">
            <h1 class="track__artist">{{ track.artists[0].name }}</h1>
            <p class="track__name">{{ track.name }}</p>
          </div>

          <div class="media-right">
            <p class="link-text">Listen on Spotify</p>
            <span class="fa fa-play play"></span>
          </div>
        </div>
      </div>
    </div>
  </a>
</template>

<script>
export default {
  props: ['track'],
  data() {
    return {
    };
  },

  methods: {

  },
};
</script>
