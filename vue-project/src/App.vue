<template>
  <TheAccordion :accordionItems="accordionItems">
    <template
      v-for="item in accordionItems"
      :key="item.name"
      v-slot:[item.name]
    >
      <p>Information of {{ item.title }}.</p>
    </template>
  </TheAccordion>
</template>

<script>
import TheAccordion from "./components/Accordion.vue";

export default {
components: {
  TheAccordion,
},
data() {
  return {
    accordionItems: [
      { name: "name1", title: "Section 1", expanded: false },
      { name: "name2", title: "Section 2", expanded: true },
      { name: "name3", title: "Section 3", expanded: false },
      { name: "name4", title: "Section 4", expanded: false },
      { name: "name5", title: "Section 5", expanded: false },
      { name: "name6", title: "Section 6", expanded: true },
    ],
  };
},
};
</script>