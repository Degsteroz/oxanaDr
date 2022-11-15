<template>
  <img :src="mapImage" class="map__Image"/>
  <iframe
      :src="iframeSrc"
      class="map__iFrame"
      width="600"
      height="450"
      style="border:0;"
      allowfullscreen=""
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
  />
</template>

<script setup>
import pageData from '../data/data'

const { iframeSrc, mapImage } = pageData

</script>

<style scoped>
.map__Image {
  height: 450px;
}
@media (max-width: 375px) {
  .map__Image {
    display: none;
  }
  .map__iFrame {
    width: 100%;
  }
}
</style>
