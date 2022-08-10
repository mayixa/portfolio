<template>
  <div class="home">
    <div class="hero">
      <div class="hero-overlay"></div>
      <div class="hero-topbar">
        <p class="position">&#60;FRONTEND DEVELOPER /&#62;</p>
        <div class="socials">
          <a class="socials-link" href="" title="LinkedIn"><IconLinkedin /></a>
          <a class="socials-link" href="" title="Facebook"><IconFacebook /></a>
          <a class="socials-link" href="" title="Github"><IconGithub /></a>
        </div>
      </div>
      <div class="hero-container">
        <h1 class="title">mayixa</h1>
        <h2 class="subtitle">Emma Borghult</h2>
      </div>
      <p class="descr">
        I AM A CREATIVE DEVELOPER BASED IN SWEDEN. I HAVE EXPERIENCE IN MANY
        VARIOUS AREAS OF WEBSITE CREATION. I LOVE NATURE, BULLTERRIERS AND
        BANANAS. <a class="descr-link" href="mailto:emmaborghult@gmail.com">contact me</a>
      </p>
      <video autoplay muted loop id="bg-video">
        <source src="../assets/bg-video.mp4" type="video/mp4" />
      </video>
    </div>
  </div>
</template>

<script>
import IconLinkedin from "@/components/icons/IconLinkedin.vue";
import IconFacebook from "@/components/icons/IconFacebook.vue";
import IconGithub from "@/components/icons/IconGithub.vue";

export default {
  name: "Home",
  components: {
    IconLinkedin,
    IconFacebook,
    IconGithub,
  },
};
</script>

<style lang="scss" scoped>
.home {
  .hero {
    &-overlay {
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
      z-index: 0;
    }
    &-topbar {
      position: absolute;
      top: 0;
      left: 0;
      display: flex;
      justify-content: space-between;
      width: 100%;
      z-index: 1;
      .position {
        font-size: 1.5rem;
        margin-bottom: 4rem;
        padding: 5rem;
      }
      .socials {
        padding: 5rem;

        &-link {
          margin-right: 1rem;
        }
      }
    }
    &-container {
      position: absolute;
      top: 7rem;
      left: 0;
      padding: 5rem;

      .title {
        font-family: "Plaster", cursive;
        font-size: 14.437rem;
        line-height: 0.93;
        mix-blend-mode: difference;
      }
      .subtitle {
        font-family: "La Belle Aurore", cursive;
        font-size: 6rem;
        line-height: 0;
      }
    }
    .descr {
      position: absolute;
      bottom: 8rem;
      right: 5rem;
      max-width: 35rem;
      text-align: right;
      font-size: 2.25rem;
      text-transform: uppercase;
      line-height: 2.5rem;
      z-index: 1;
      &-link {
        text-transform: lowercase;
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
