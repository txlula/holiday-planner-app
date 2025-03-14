<script setup lang="ts">
import Button from 'primevue/button'
import { ref } from 'vue'
import HomePage from './components/HomePage.vue'
import SchedulePage from './components/SchedulePage.vue'
import MapPage from './components/MapPage.vue'

const currentTab = ref('Home')

const tabs = {
  Home: HomePage,
  Schedule: SchedulePage,
  Map: MapPage,
}

const icons = {
  Home: 'pi pi-home',
  Schedule: 'pi pi-calendar',
  Map: 'pi pi-map',
}
</script>

<template>
  <header>
    <div class="header">
      <div class="title">
        <h1>Holiday Planner App</h1>
      </div>

      <div class="navigation-bar">
        <Button
          v-for="(_, tab) in tabs"
          :key="tab"
          :label="tab"
          :icon="icons[tab]"
          @click="currentTab = tab"
        />
      </div>
    </div>
  </header>

  <main>
    <component :is="tabs[currentTab]"></component>
  </main>
</template>

<style scoped>
.header {
  border-radius: 10px;
  padding: 10px 20px 10px 20px;
  background-color: #30c5ff;
  display: flex;
  color: white;
}

.navigation-bar {
  display: flex;
}

.navigation-button {
  margin: 0px 10px 0px 10px;
}
</style>
