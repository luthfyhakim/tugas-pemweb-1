<script setup>
  import ClickCounter from './components/ClickCounter.vue';
  import BoxColorChanger from './components/BoxColorChanger.vue';
  import ImageCarousel from './components/ImageCarousel.vue';
</script>

<template>
  <header>
    <h1>Tugas Pemweb 1</h1>
  </header>

  <main>
    <!-- Click Counter -->
    <ClickCounter />

    <!-- Box Color Changer -->
    <BoxColorChanger />

    <!-- Image Carousel -->
    <ImageCarousel />
  </main>
</template>

<style scoped>
  header {
    background-color: var(--primary-color);
    color: white;
    padding: 20px;
    text-align: center;
    position: sticky;
    top: 0;
    z-index: 1000;
  }

  h1 {
    margin: 0;
  }

  main {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    padding: 20px 0;
  }
</style>
