<template>
  <q-footer class="text-center">
    <q-toolbar>
      <q-toolbar-title>© Copyright 2024 </q-toolbar-title>
    </q-toolbar>
  </q-footer>
</template>

<script>
import { defineComponent } from 'vue';
import { QFooter, QToolbar, QToolbarTitle } from 'quasar';

export default defineComponent({
  components: {
    QFooter,
    QToolbar,
    QToolbarTitle
  }
});
</script>

<style scoped>
.text-center{
  background-color: darkgrey;
}
</style>
