<template>
    <div class="accordion">
      <div v-for="item in accordionItems" :key="item.name">
        <div class="accordion-header" @click="toggleItem(item)">
          {{ item.title }}
          <span v-if="item.expanded">-</span>
          <span v-else>+</span>
        </div>
        <div v-if="item.expanded" class="accordion-content">
          <slot :name="item.name"></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      accordionItems: {
        type: Array,
        required: true,
      },
    },
    methods: {
      toggleItem(item) {
        item.expanded = !item.expanded;
      },
    },
  };
  </script>
  
  <style scoped>
  .accordion {
    border: 1px solid #fff;
    background: #000;
    color: #fff;
  }
  
  .accordion-header {
    cursor: pointer;
    padding: 10px;
    background-color: #000;
    border-bottom: 1px solid #fff;
    display: flex;
    justify-content: space-between;
  }
  
  .accordion-content {
    padding: 10px;
    border-bottom: 1px solid #fff;
  }
  </style>