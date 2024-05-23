<template>
  <q-card class="movie-card">
    <q-img :src="poster" class="movie-poster" />
    <q-card-section class="movie-details">
      <div class="text-h6">{{ title }}</div>
      <div class="text-subtitle2">Jadwal: {{ schedule }}</div>
    </q-card-section>
    <q-card-actions align="right">
      <q-btn class="btn" flat label="Beli Tiket" color="tombol" @click="$emit('buy-ticket')" />
    </q-card-actions>
  </q-card>
</template>

<script>
import { defineComponent } from 'vue';
import { QCard, QImg, QCardSection, QCardActions, QBtn } from 'quasar';

export default defineComponent({
  name: 'MovieCard',
  props: {
    poster: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    schedule: {
      type: String,
      required: true
    }
  },
  components: {
    QCard,
    QImg,
    QCardSection,
    QCardActions,
    QBtn
  }
});
</script>

<style scoped>
.movie-card {
  width: 300px; 
  display: flex;
  flex-direction: column;
  height: 500px;
  background-color: rgba(170, 169, 173, 0.7); 
  box-shadow: 0 0 10px #D3D3D3;
}
.movie-card:hover{
  width: 350px;
  height: 525;
}
.movie-poster {
  max-height: 100%;
}

.movie-details {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.btn{
  border: 1px solid #ffff;
}
</style>
