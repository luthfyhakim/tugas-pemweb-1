<template>
  <section class="card">
    <h2>1. Click Counter</h2>
    <div class="content">
      <p class="count">Count: {{ count }}</p>
      <button @click="incrementCount" class="btn">Increment</button>
    </div>
  </section>
</template>

<script>
  import { ref } from 'vue';
  
  export default {
    data() {
      return {
        count: ref(0),
      };
    },
    
    methods: {
      incrementCount() {
        this.count++;
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

  .count {
    font-size: 24px;
    font-weight: bold;
    margin: 10px 0;
    color: var(--primary-color);
  }
</style>
