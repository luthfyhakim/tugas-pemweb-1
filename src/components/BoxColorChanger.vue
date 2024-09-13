<template>
  <section class="card">
    <h2>2. Box Color Changer</h2>
    <div class="content">
      <div class="color-box" :style="{ backgroundColor: boxColor }"></div>
      <button @click="changeColor" class="btn">Change Color</button>
    </div>
  </section>
</template>

<script>
  export default {
    data() {
      return {
        boxColor: 'lightblue',
      };
    },
    
    methods: {
      changeColor() {
        this.boxColor = `rgb(${Math.random() * 255}, ${Math.random() * 255}, ${Math.random() * 255})`;
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

  .color-box {
    width: 100px;
    height: 100px;
    margin: 10px 0;
    border-radius: 8px;
    transition: background-color 0.3s;
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
</style>
