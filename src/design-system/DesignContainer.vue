<script setup>
  import { ref, reactive, defineProps } from 'vue';

  import ColorCard from '@/design-system/ColorCard.vue';
  import GradientCard from './GradientCard.vue';
  import TypographyCard from './TypographyCard.vue';

  const props = defineProps({
    object: Object,
  });

  const colorGroup = reactive(props.object);

  const title = ref(colorGroup.category);

  const isColor = checkColor();

  function checkColor() {
    return title.value.toLowerCase() === 'colors';
  }

  const isGradient = checkGradient();

  function checkGradient() {
    return title.value.toLowerCase() === 'gradients';
  }

  const isTypography = checkTypography();

  function checkTypography() {
    return title.value.toLowerCase() === 'typography';
  }

  const groups = reactive(colorGroup.groups);
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <ColorCard v-if="isColor" :groups="groups"></ColorCard>
    <GradientCard v-if="isGradient" :groups="groups"></GradientCard>
    <TypographyCard v-if="isTypography" :groups="groups"></TypographyCard>
  </div>
</template>

<style scoped>
  div {
    padding-inline: 10em;
  }

  h1 {
    text-transform: capitalize;
    padding-top: 72px;
  }
</style>
