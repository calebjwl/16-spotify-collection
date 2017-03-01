<template lang="html">
  <div class="track">
    <div class="panel-block media">
      <div class="media-left">
        <div class="track__frame">
          <img src="http://placecera.com/100/100" alt="" class="track__media">
        </div>
      </div>

      <div class="media-content">
        <h1 class="track__artist">Ketty purry</h1>
        <p class="track__name">Firework</p>
      </div>

      <div class="media-right">
        <span class="fa fa-spotify spotify"></span>
      </div>
    </div>
  </div>
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
