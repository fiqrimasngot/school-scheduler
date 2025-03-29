<script setup>
import "vue3-carousel/carousel.css";
import { Carousel, Slide, Navigation } from "vue3-carousel";

const images = Array.from({ length: 10 }, (_, index) => ({
  id: index + 1,
  url: `https://picsum.photos/seed/${Math.random()}/800/600`,
}));

const config = {
  height: 650,
  itemsToShow: 1 /* Show only 1 image */,
  gap: 5,
  autoplay: 4000,
  wrapAround: true,
  pauseAutoplayOnHover: true,
};
</script>

<template>
  <div class="my-12">
    <Carousel v-bind="config" transition="fade">
      <Slide v-for="image in images" :key="image.id">
        <img :src="image.url" alt="image" />
      </Slide>

      <template #addons>
        <Navigation />
      </template>
    </Carousel>
  </div>
</template>

<style>
:root {
  background-color: #242424;
}

.carousel {
  --vc-nav-background: rgba(255, 255, 255, 0.7);
  --vc-nav-border-radius: 100%;
}

img {
  border-radius: 8px;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Hide left and right navigation buttons */
.carousel__prev,
.carousel__next {
  display: none !important;
}

.carousel__slide {
  transition: opacity 1.5s ease-out, transform 1.5s ease-out;
  opacity: 0;
  transform: scale(0.95) translateY(0);
}

.carousel__slide--active {
  opacity: 1;
  transform: scale(1) translateY(0);
}
</style>
