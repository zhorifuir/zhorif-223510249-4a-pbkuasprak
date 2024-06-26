<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-black text-white" elevated>
      <q-toolbar>
        <q-toolbar-title>
          <div class="text-h5">Weather Apps</div>
        </q-toolbar-title>
        <q-space />
        <!-- Updated Dropdown Button -->
        <div class="q-pa-md">
          <q-btn-dropdown color="dark" label="Dropdown Button">
            <q-list>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/1')">
                <q-item-section>
                  <q-item-label>Tugas 1</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/2')">
                <q-item-section>
                  <q-item-label>Tugas 2</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/3')">
                <q-item-section>
                  <q-item-label>Tugas 3</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/4')">
                <q-item-section>
                  <q-item-label>Tugas 4</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/5')">
                <q-item-section>
                  <q-item-label>Tugas 5</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/6')">
                <q-item-section>
                  <q-item-label>Tugas 6</q-item-label>
                </q-item-section>
              </q-item>
              <q-item clickable v-close-popup @click="navigateTo('/assignment/7')">
                <q-item-section>
                  <q-item-label>Tugas 7</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="bg-black text-white">
      <q-toolbar>
        <q-toolbar-title>
          <div class="text-subtitle1">© 2024 Zhorif | Teknik Informatika.</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'App',
  methods: {
    navigateTo(route) {
      this.$router.push(route);
    },
    onItemClick() {
      // Implement the logic for item click if needed
    }
  }
};
</script>

<style>
.text-h5 {
  font-size: 1.25rem;
  font-weight: 500;
}

.text-subtitle1 {
  font-size: 1rem;
  font-weight: 400;
}

.bg-black {
  background-color: #000000;
}

.q-pa-md {
  padding: 16px;
}
</style>
