<template>
  <q-layout view="hHh lpR fFf">
    <Navbar />

    <q-page-container>
      <q-page padding>
        <Carousel />
        <div class="movie-container q-mt-lg q-gutter-lg row justify-around">
          <MovieCard
            v-for="movie in movies"
            :key="movie.id"
            :poster="movie.poster"
            :title="movie.title"
            :schedule="movie.schedule"
            @buy-ticket="handleBuyTicket(movie)"
          />
          <div v-if="movies.length < 4" v-for="i in 4 - movies.length" :key="i" class="movie-placeholder">
          </div>
        </div>
      </q-page>
    </q-page-container>

    <Footer />
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue';
import { QLayout, QPageContainer, QPage } from 'quasar';
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import MovieCard from './components/MovieCard.vue';
import Footer from './components/Footer.vue';

export default defineComponent({
  components: {
    QLayout,
    QPageContainer,
    QPage,
    Navbar,
    Carousel,
    MovieCard,
    Footer
  },
  data() {
    return {
      movies: [
        {
          id: 1,
          poster: 'https://jadwalnonton.com/data/images/movies/2024/kingdom-of-the-planet-of-the-apes-cnp_300x450.webp',
          title: 'KINGDOM OF THE PLANET OF THE APES',
          schedule: '10:00 AM'
        },
        {
          id: 2,
          poster: 'https://jadwalnonton.com/data/images/movies/2024/furiosa-a-mad-max-saga-cnp_300x450.webp',
          title: 'FURIOSA: A MAD MAX SAGA',
          schedule: '18:00 PM'
        },
        {
          id: 2,
          poster: 'https://jadwalnonton.com/data/images/movies/2024/civil-war_300x450.webp',
          title: 'CIVIL WAR',
          schedule: '19:00 PM'
        },
        {
          id: 2,
          poster: 'https://jadwalnonton.com/data/images/movies/2023/tx-almarhum_300x450.webp',
          title: 'ALMARHUM',
          schedule: '19:45 PM'
        }
      ]
    };
  },
  methods: {
    handleBuyTicket(movie) {
      console.log(`Buying ticket for ${movie.title}`);
    }
  }
});
</script>

<style>
.q-mt-lg {
  margin-top: 2rem;
}
.q-gutter-lg {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
.row {
  display: flex;
  flex-wrap: wrap;
}
.justify-around {
  justify-content: space-around;
}
.movie-container {
  justify-content: center;
}
.movie-placeholder {
  width: 300px;
  opacity: 0; 
}

</style>
