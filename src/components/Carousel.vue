<template>
  <div class="q-pa-md">
    <q-carousel
      arrows
      :autoplay ="true"
      :autoplay-speed="1000"
      animated
      v-model="slide"
      height="400px"
    >
      <q-carousel-slide name="first" img-src="https://idseducation.com/wp-content/uploads/2022/06/imgonline-com-ua-CompressToSize-dZw4zfvWMZV0.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">MINIONS: THE RISE OF GRU</div>
          <div class="text-subtitle1">Coming Soon</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="second" img-src="https://images.thedirect.com/media/article_full/deadpool-3-rating.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Deadpool 3</div>
          <div class="text-subtitle1">Coming Soon</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="third" img-src="https://i.ytimg.com/vi/WWLmohqJBUI/maxresdefault.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Venom 3</div>
          <div class="text-subtitle1">Coming Soon</div>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import { QCarousel, QCarouselSlide } from 'quasar';

export default defineComponent({
  name: 'Carousel',
  components: {
    QCarousel,
    QCarouselSlide
  },
  setup() {
    const slide = ref('first');
    return {
      slide
    };
  }
});
</script>

<style>
.custom-caption {
  background-color: rgba(0, 0, 0, 0.5);
  padding: 1rem;
  color: white;
}
</style>
