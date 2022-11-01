<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
import Header from "./components/Header.vue";
</script>

<template>
  <header class="section1">
    <Header />
    <p class="descr">
      I AM A CREATIVE DEVELOPER BASED IN SWEDEN. I HAVE EXPERIENCE IN MANY
      VARIOUS AREAS OF WEBSITE CREATION. I LOVE NATURE, BULLTERRIERS AND
      BANANAS.
      <a class="descr-link" href="mailto:emmaborghult@gmail.com">
        contact me
      </a>
    </p>
  </header>
  <main>
    <!-- TEMPORARY -->
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aspernatur
      placeat velit dicta sit impedit quis corrupti esse cupiditate earum
      veritatis eaque repellendus cum, atque aliquid nihil, quibusdam harum
      natus porro!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aspernatur
      placeat velit dicta sit impedit quis corrupti esse cupiditate earum
      veritatis eaque repellendus cum, atque aliquid nihil, quibusdam harum
      natus porro!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aspernatur
      placeat velit dicta sit impedit quis corrupti esse cupiditate earum
      veritatis eaque repellendus cum, atque aliquid nihil, quibusdam harum
      natus porro!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aspernatur
      placeat velit dicta sit impedit quis corrupti esse cupiditate earum
      veritatis eaque repellendus cum, atque aliquid nihil, quibusdam harum
      natus porro!
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aspernatur
      placeat velit dicta sit impedit quis corrupti esse cupiditate earum
      veritatis eaque repellendus cum, atque aliquid nihil, quibusdam harum
      natus porro!
    </p>
  </main>
  <!-- <RouterView /> -->
</template>

<style lang="scss" scoped>
.descr {
  position: absolute;
  bottom: 6rem;
  right: var(--container-spacing);
  max-width: 35rem;
  text-align: right;
  font-size: clamp(1rem, 2vw + 0.75rem, 2.25rem);
  text-transform: uppercase;
  line-height: 1.3;
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
</style>
