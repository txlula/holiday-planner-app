<script setup lang="ts">
import { GoogleMap, Marker } from 'vue3-google-map'

const center = { lat: 40.689247, lng: -74.044502 }
const GOOGLE_API_KEY = import.meta.env.VITE_API_GOOGLE_API_KEY
</script>

<template>
  <div class="map">
    <GoogleMap
      :api-key="GOOGLE_API_KEY"
      style="width: 100%; height: 500px"
      :center="center"
      :zoom="15"
    >
      <Marker :options="{ position: center }" />
    </GoogleMap>
  </div>
</template>

<style scoped>
.map {
  margin: 20px 0px 20px 0px;
}
</style>
