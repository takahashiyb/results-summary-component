<script setup>
  import { ref, reactive } from 'vue';

  const props = defineProps({
    groups: Object,
  });

  const items = reactive(props.groups);
</script>

<template>
  <div v-for="item in items" :key="item.name">
    <h2>
      <span>{{ item.name }}</span
      >{{ item['font-family'] }}
    </h2>
    <div class="text-content">
      <p>{{ item['font-size'] }}</p>
      <p>{{ item['line-height'] }}</p>
      <p>{{ item['letter-spacing'] }}</p>
    </div>
    <hr />
    <p :style="{ font: `var(${item.variable})` }">{{ item['sample-text'] }}</p>
  </div>
</template>

<style scoped>
  .text-content {
    display: flex;
    gap: 12px;
  }

  h2 {
    text-transform: capitalize;
    padding-top: 72px;
  }

  p {
    font: var(--font-preset-6-m);
  }

  span {
    display: inline-block;
    text-transform: uppercase;
    color: slategray;

    padding-right: 1em;
  }
</style>
