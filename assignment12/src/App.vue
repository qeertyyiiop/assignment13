<template>
  <TheCarousel :items="carouselItems"></TheCarousel>
</template>

<script>
import TheCarousel from "./components/Carousel.vue";
export default {
  components: {
    TheCarousel,
  },
  data() {
    return {
      carouselItems: [
        {
          src: "https://dynamic-media-cdn.tripadvisor.com/media/photo-o/0f/ba/29/5c/img-worlds-of-adventure.jpg?w=1200&h=-1&s=1",
          alt: "Image 1",
          caption: "Caption for Image 1",
        },
        {
          src: "https://media.tacdn.com/media/attractions-splice-spp-674x446/07/c3/95/c8.jpg",
          alt: "Image 2",
          caption: "Caption for Image 2",
        },
      ],
    };
  },
};
</script>