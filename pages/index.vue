<template>
  <v-progress-circular
    class="ma-auto"
    :size="100"
    color="white"
    indeterminate
  ></v-progress-circular>
</template>

<script>
export default {
  data () {
    return {
      audio: new Audio()
    }
  },
  methods: {
    PlayAudio () {
      const app = this
      if (app.audio.paused) {
        app.audio.play();
      }
    }
  },
  async mounted () {
    const app = this
    app.audio.src = "/knock.mp3";
    app.audio.autoplay = true;
    app.audio.loop  = true;
    app.audio.volume = 1
    document.addEventListener("click", () => {
      app.PlayAudio()
    })
  }
}
</script>

<style scoped>
.pager {
  height: 100vh!important;
  width: 100vw!important;
}
.pager-content {
  margin: auto!important;
}
</style>