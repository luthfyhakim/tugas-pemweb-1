<template>
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
</template>

<script>
  export default {
    data() {
      return {
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
