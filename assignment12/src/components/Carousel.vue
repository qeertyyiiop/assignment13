<template>
    <div class="carousel">
      <div
        class="carousel-inner"
        :style="{ transform: 'translateX(' + translateValue + '%)' }"
      >
        <div v-for="(item, index) in items" :key="index" class="carousel-item">
          <img :src="item.src" :alt="item.alt" class="carousel-image" />
          <div class="carousel-caption" v-if="item.caption">
            {{ item.caption }}
          </div>
        </div>
      </div>
      <button @click="prev" class="carousel-control left">❮</button>
      <button @click="next" class="carousel-control right">❯</button>
    </div>
  </template>
  <script>
  export default {
    props: {
      items: Array,
    },
    data() {
      return {
        currentIndex: 0,
        translateValue: 0,
      };
    },
    methods: {
      next() {
        if (this.currentIndex < this.items.length - 1) {
          this.currentIndex++;
          this.translateValue -= 100;
        }
      },
      prev() {
        if (this.currentIndex > 0) {
          this.currentIndex--;
          this.translateValue += 100;
        }
      },
    },
  };
  </script>
  <style scoped>
  .carousel {
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
  }
  
  .carousel-inner {
    display: flex;
    transition: transform 0.5s ease-in-out;
  }
  
  .carousel-item {
    flex: 0 0 100%;
    box-sizing: border-box;
  }
  
  .carousel-image {
    width: 100%;
    height: auto;
  }
  
  .carousel-caption {
    text-align: center;
    margin-top: 10px;
  }
  
  .carousel-control {
    color: #fff;
    position: absolute;
    top: 50%;
    font-size: 24px;
    background: none;
    border: none;
    cursor: pointer;
  }
  
  .left {
    left: 10px;
    transform: translateY(-50%);
  }
  
  .right {
    right: 10px;
    transform: translateY(-50%);
  }
  
  .carousel-control:hover {
    color: #333;
  }
  </style>