<template>
  <div class="header">
    <div
      class="header-overlay"
      :style="{
        background: 'linear-gradient( 0deg,' + color1 + ',' + color2 + ')',
      }"
    ></div>
    <div class="header-topbar">
      <p class="position">&#60;FRONTEND DEVELOPER /&#62;</p>
      <div class="actions">
        <button
          @click="togglePicker"
          class="color-picker"
          title="Pick a new gradient color"
        >
          <span :style="{ 'background-color': color2 }"></span>
        </button>
        <div v-if="openPicker" class="color-picker__popup">
          <color-picker
            v-model:pureColor="color2"
            :isWidget="true"
            :zIndex="3"
            @blur="openPicker = false"
          />
        </div>
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
    <div class="header-container">
      <h1 class="title">mayixa</h1>
      <h2 class="subtitle">Emma Borghult</h2>
    </div>

    <video autoplay muted loop id="bg-video">
      <source src="../assets/bg-video.mp4" type="video/mp4" />
    </video>
  </div>
</template>

<script setup lang="ts">
import IconLinkedin from "./icons/IconLinkedin.vue";
import IconFacebook from "./icons/IconFacebook.vue";
import IconGithub from "./icons/IconGithub.vue";
import { ColorPicker } from "vue3-colorpicker";
import "vue3-colorpicker/style.css";
import type { ColorInputWithoutInstance } from "tinycolor2";
import { ref } from "vue-demi";

const color1 = ref<ColorInputWithoutInstance>("rgba(152, 94, 188, 0.2)");
const color2 = ref<ColorInputWithoutInstance>("rgba(24, 89, 193, 0.2)");
let openPicker = ref<boolean>(false);

const togglePicker = () => {
  openPicker.value = !openPicker.value;
};
</script>

<style lang="scss" scoped>
.header {
  height: 100vh;
  min-height: 550px;
  &-overlay {
    position: absolute;
    top: 0;
    left: 0;
    height: 100vh;
    min-height: 550px;
    width: 100%;
    z-index: 1;
  }
  &-topbar {
    position: absolute;
    top: var(--container-spacing);
    left: 0;
    display: grid;
    grid-template-columns: 75% 1fr;
    grid-gap: 0.5rem;
    padding: 0.5rem var(--container-spacing);
    width: 100%;
    z-index: 2;

    @media (min-width: 768px) {
      grid-template-columns: repeat(2, 1fr);
    }
    .color-picker {
      border-radius: 3px;
      border: 2px solid var(--soft);
      height: 31px;
      width: 40px;
      cursor: pointer;

      @media (min-width: 768px) {
        margin-right: 2rem;
      }
      span {
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        top: 0;
      }
      &__popup {
        position: absolute;
        top: 4rem;
      }
    }
    .position {
      font-size: clamp(0.875rem, 1vw + 1rem, 1.5rem);
      line-height: 1.2;
      display: flex;
      align-items: center;

      @media (min-width: 768px) {
        justify-content: flex-start;
      }
    }
    .actions {
      display: flex;
      align-items: center;
      justify-content: flex-end;
    }
    .socials {
      display: none;

      @media (min-width: 768px) {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-gap: 0.5rem;
      }
      &-link {
        display: inline-block;
        svg {
          width: 2.2rem;

          @media (min-width: 768px) {
            width: unset;
          }
        }
      }
    }
  }
  &-container {
    position: absolute;
    top: 7rem;
    left: 0;
    padding: 1rem;

    @media (min-width: 426px) {
      padding: var(--container-spacing);
    }
    .title {
      font-family: "Plaster", cursive;
      line-height: 0.93;
      mix-blend-mode: difference;
      z-index: 1;
      font-size: 4.4rem;

      @media (min-width: 426px) {
        font-size: clamp(5rem, 9vw + 3rem, 14.438rem);
      }
    }
    .subtitle {
      font-family: "La Belle Aurore", cursive;
      line-height: 0;
      z-index: 1;
      mix-blend-mode: difference;
      color: white;
      font-size: 2rem;

      @media (min-width: 426px) {
        font-size: clamp(1rem, 3vw + 1.8rem, 6rem);
      }
    }
  }
}
#bg-video {
  height: 100vh;
  min-height: 550px;
  width: 100%;
  object-fit: cover;
}
div[data-popper-placement="bottom"] {
  position: absolute !important;
  right: -2rem !important;
}
</style>
