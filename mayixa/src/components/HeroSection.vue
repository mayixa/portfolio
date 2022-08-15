<template>
  <header class="hero">
    <div
      class="hero-overlay"
      :style="{
        background: 'linear-gradient( 0deg,' + color1 + ',' + color2 + ')',
      }"
    ></div>
    <div class="hero-topbar">
      <p class="position">&#60;FRONTEND DEVELOPER /&#62;</p>
      <!-- <color-picker v-model:pureColor="color1" /> -->
      <div class="actions">
        <label class="color-picker">
          <span>Change gradient color</span>
          <color-picker v-model:pureColor="color2" />
        </label>
        <div class="socials">
          <a
            class="socials-link"
            href="https://www.linkedin.com/in/emma-borghult"
            title="LinkedIn"
            ><IconLinkedin
          /></a>
          <a
            class="socials-link"
            href="https://www.facebook.com/emma.borghult"
            title="Facebook"
            ><IconFacebook
          /></a>
          <a
            class="socials-link"
            href="https://github.com/mayixa"
            title="Github"
            ><IconGithub
          /></a>
        </div>
      </div>
    </div>
    <div class="hero-container">
      <h1 class="title">mayixa</h1>
      <h2 class="subtitle">Emma Borghult</h2>
    </div>
    <p class="descr">
      I AM A CREATIVE DEVELOPER BASED IN SWEDEN. I HAVE EXPERIENCE IN MANY
      VARIOUS AREAS OF WEBSITE CREATION. I LOVE NATURE, BULLTERRIERS AND
      BANANAS.
      <a class="descr-link" href="mailto:emmaborghult@gmail.com">
        contact me
      </a>
    </p>
    <video autoplay muted loop id="bg-video">
      <source src="../assets/bg-video.mp4" type="video/mp4" />
    </video>
  </header>
</template>

<script setup lang="ts">
import IconLinkedin from "../components/icons/IconLinkedin.vue";
import IconFacebook from "../components/icons/IconFacebook.vue";
import IconGithub from "../components/icons/IconGithub.vue";
import { ColorPicker } from "vue3-colorpicker";
import "vue3-colorpicker/style.css";
import { ColorInputWithoutInstance } from "tinycolor2";
import { ref } from "vue-demi";

const color1 = ref<ColorInputWithoutInstance>("rgba(152, 94, 188, 0.2)");
const color2 = ref<ColorInputWithoutInstance>("rgba(24, 89, 193, 0.2)");
const gradientColor = ref(
  "linear-gradient(0deg, rgba(0, 0, 0, 1) 0%, rgba(0, 0, 0, 1) 100%)"
);
</script>

<style lang="scss" scoped>
.hero {
  &-overlay {
    position: absolute;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100%;
    z-index: 1;
  }
  &-topbar {
    position: absolute;
    top: 5rem;
    left: 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.5rem 5rem;
    width: 100%;
    z-index: 1;
    .color-picker {
      background: #f5eee6;
      mix-blend-mode: difference;
      color: black;
      display: flex;
      align-items: center;
      padding: 0.25rem 0 0.25rem 0.5rem;
      border-radius: 3px;
      margin-right: 2rem;
      span {
        margin-right: 0.5rem;
      }
    }
    .position {
      font-size: 1.5rem;
    }
    .actions {
      display: flex;
      align-items: center;
    }
    .socials {
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
      z-index: 1;
    }
    .subtitle {
      font-family: "La Belle Aurore", cursive;
      font-size: 6rem;
      line-height: 0;
      z-index: 1;
      mix-blend-mode: difference;
      color: white;
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
      position: absolute;
      bottom: -2.2rem;
      right: 0;
      text-transform: lowercase;
      display: block;
      transition: all 0.3s ease-in-out;
      &::before {
        content: "";
        background-color: #f5eee6;
        position: absolute;
        left: 0;
        bottom: 3px;
        width: 100%;
        height: 3px;
        z-index: -1;
        transition: all 0.3s ease-in-out;
      }

      &:hover {
        color: black;

        &::before {
          bottom: 0;
          height: 90%;
        }
      }
    }
  }
}
#bg-video {
  height: 100vh;
  width: 100%;
  object-fit: cover;
}
</style>
