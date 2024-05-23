<template>
  <q-header elevated class="heder">
    <q-toolbar>
      <q-btn flat round dense icon="menu" @click="drawer = !drawer" />
      <q-toolbar-title class="titel">Movie XXVX</q-toolbar-title>
      <q-btn flat round dense :icon="darkMode ? 'light_mode' : 'dark_mode'" @click="toggleDarkMode" />
    </q-toolbar>
    <q-drawer v-model="drawer" side="left" overlay>
      <q-list>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="account_circle" :class="{'dark-mode-icon': darkMode, 'light-mode-icon': !darkMode}" />
          </q-item-section>
          <q-item-section>
            <q-item-label class="item-label">Account</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="payment" :class="{'dark-mode-icon': darkMode, 'light-mode-icon': !darkMode}" />
          </q-item-section>
          <q-item-section>
            <q-item-label class="item-label">Payment</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="card_giftcard" :class="{'dark-mode-icon': darkMode, 'light-mode-icon': !darkMode}" />
          </q-item-section>
          <q-item-section>
            <q-item-label class="item-label">Voucher</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="settings" :class="{'dark-mode-icon': darkMode, 'light-mode-icon': !darkMode}" />
          </q-item-section>
          <q-item-section>
            <q-item-label class="item-label">Setting</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple @click="toggleDarkMode">
          <q-item-section avatar>
            <q-icon :name="darkMode ? 'light_mode' : 'dark_mode'" :class="{'dark-mode-icon': darkMode, 'light-mode-icon': !darkMode}" />
          </q-item-section>
          <q-item-section>
            <q-item-label class="item-label">{{ darkMode ? 'Light Mode' : 'Dark Mode' }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
  </q-header>
</template>
<script>
import { defineComponent } from 'vue';
import { QHeader, QToolbar, QBtn, QToolbarTitle, QDrawer, QList, QItem, QItemSection, QItemLabel, QIcon } from 'quasar';

export default defineComponent({
  data() {
    return {
      drawer: false,
      darkMode: this.$q.dark.isActive // Initialize dark mode state
    };
  },
  methods: {
    toggleDarkMode() {
      this.$q.dark.toggle();
      this.darkMode = this.$q.dark.isActive; // Update dark mode state
    }
  },
  components: {
    QHeader,
    QToolbar,
    QBtn,
    QToolbarTitle,
    QDrawer,
    QList,
    QItem,
    QItemSection,
    QItemLabel,
    QIcon
  }
});
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Serif:ital,wght@0,100..900;1,100..900&display=swap');

.item-label {
  color: black;
}

.q-dark .item-label {
  color: white;
}

.light-mode-icon {
  color: black;
}

.dark-mode-icon {
  color: white;
}

.heder{
  background-color: #A9A9A9;
}

.titel{
  font-weight: bold;
  font-family: "Noto Serif", serif;
}
</style>
