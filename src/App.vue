<template>
  <header>
    <h1>Tugas Pemweb 1</h1>
  </header>
    
  <main>
    <!-- Click Counter -->
    <section class="card">
      <h2>1. Click Counter</h2>
      <div class="content">
        <p class="count">Count: {{ count }}</p>
        <button @click="incrementCount" class="btn">Increment</button>
      </div>
    </section>

    <!-- Box Color Changer -->
    <section class="card">
      <h2>2. Box Color Changer</h2>
      <div class="content">
        <div class="color-box" :style="{ backgroundColor: boxColor }"></div>
        <button @click="changeColor" class="btn">Change Color</button>
      </div>
    </section>

    <!-- Image Carousel -->
    <section class="card">
      <h2>3. Image Carousel</h2>
      <div class="content">
        <img :src="currentImage" alt="Carousel Image" class="carousel-image" />
        <div class="carousel-controls">
          <button @click="prevImage" class="btn">Previous</button>
          <button @click="nextImage" class="btn">Next</button>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
  export default {
    data() {
      return {
        count: 0,
        boxColor: 'lightblue',
        images: [
          'https://picsum.photos/id/1018/400/300',
          'https://picsum.photos/id/1015/400/300',
          'https://picsum.photos/id/1019/400/300',
          'https://picsum.photos/id/1016/400/300',
          'https://picsum.photos/id/1021/400/300'
        ],
        currentImageIndex: 0,
      };
    },
    
    computed: {
      currentImage() {
        return this.images[this.currentImageIndex];
      },
    },
    
    methods: {
      incrementCount() {
        this.count++;
      },
      
      changeColor() {
        this.boxColor = `rgb(${Math.random() * 255}, ${Math.random() * 255}, ${Math.random() * 255})`;
      },
      
      nextImage() {
        this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
      },
      
      prevImage() {
        this.currentImageIndex = (this.currentImageIndex - 1 + this.images.length) % this.images.length;
      },
    },
  };
</script>

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

.card {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
}

h2 {
  color: var(--primary-color);
  margin-top: 0;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.btn {
  background-color: var(--accent-color);
  color: white;
  border: none;
  padding: 10px 20px;
  margin: 10px 0;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.btn:hover {
  background-color: var(--primary-color);
}

.count {
  font-size: 24px;
  font-weight: bold;
  margin: 10px 0;
  color: var(--primary-color);
}

.color-box {
  width: 100px;
  height: 100px;
  margin: 10px 0;
  border-radius: 8px;
  transition: background-color 0.3s;
}

.carousel-image {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}

.carousel-controls {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-top: 10px;
}
</style>
