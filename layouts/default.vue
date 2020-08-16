<template>
  <v-app dark>
    <nuxt />
  </v-app>
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
    app.audio.src = "knock.mp3";
    app.audio.autoplay = true;
    app.audio.loop  = true;
    app.audio.volume = 1
    document.addEventListener("click", () => {
      app.PlayAudio()
    })
  }
}
</script>

<style>
html {
  overflow-x: hidden;
  overflow-y: hidden;
}

::-webkit-scrollbar {
  height: 0.0rem;
  width: 0.0rem;
}
</style>