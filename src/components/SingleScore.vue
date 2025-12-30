<script setup>
  import { reactive } from 'vue';

  const props = defineProps({
    data: Object,
  });

  const items = reactive(props.data);
</script>

<template>
  <div :class="['single-score-form', `${items.category.toLowerCase()}`]">
    <div class="container__img">
      <img :src="`${items.icon}`" />
    </div>
    <p class="category">{{ items.category }}</p>
    <p class="actual">{{ items.score }} <span class="total"> / 100</span></p>
  </div>
</template>

<style scoped>
  .single-score-form {
    display: grid;
    grid-template-columns: max-content auto max-content;

    gap: var(--spacing-0200);

    padding: var(--spacing-0200);

    border-radius: 12px;
  }

  .reaction {
    background-color: hsl(var(--red-050-color));
    color: hsl(var(--red-400-color));
  }

  .memory {
    background-color: hsl(var(--yellow-050-color));
    color: hsl(var(--yellow-800-color));
  }

  .verbal {
    background-color: hsl(var(--green-050-color));
    color: hsl(var(--green-500-color));
  }

  .visual {
    background-color: hsl(var(--blue-050-color));
    color: hsl(var(--blue-800-color));
  }

  .category {
    font: var(--font-preset-5-m);
  }

  .actual {
    color: hsl(var(--navy-950-color));
    font: var(--font-preset-5-b);
  }

  .total {
    opacity: 50%;
  }
</style>
