<template>
  <div class="home">
    <div class="hero">
      <div class="hero-container">
        <h1 class="title">mayixa</h1>
        <h2 class="subtitle">Emma Borghult</h2>
      </div>
      <video autoplay muted loop id="bg-video">
        <source src="../assets/bg-video.mp4" type="video/mp4" />
      </video>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld,
  },
};
</script>
<style lang="scss" scoped>
.home {
  .hero {
    &-container {
      background: linear-gradient(
        0deg,
        rgba(114, 235, 127, 0.2),
        rgba(114, 235, 127, 0.2)
      );
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      .title {
        font-family: "Plaster", cursive;
        font-size: 14.437rem;
        line-height: 0.93;
        mix-blend-mode: difference;
        padding: 5rem 5rem 0;
      }
      .subtitle {
        font-family: "La Belle Aurore", cursive;
        font-size: 6rem;
        line-height: 0;
        padding: 0 5rem;
      }
    }
  }
  #bg-video {
    height: 100vh;
    width: 100%;
    object-fit: cover;
  }
}
</style>
