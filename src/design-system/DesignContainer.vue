<script setup>
  import { ref, reactive, defineProps } from 'vue';

  import ColorCard from '@/design-system/ColorCard.vue';
  import GradientCard from './GradientCard.vue';
  import TypographyCard from './TypographyCard.vue';
  import SpacingCard from './SpacingCard.vue';
  import ScoreCard from '@/components/ScoreCard.vue';

  const props = defineProps({
    object: Object,
  });

  const colorGroup = reactive(props.object);

  const title = ref(colorGroup.category);

  function checkColor() {
    return title.value.toLowerCase() === 'colors';
  }

  function checkGradient() {
    return title.value.toLowerCase() === 'gradients';
  }

  function checkTypography() {
    return title.value.toLowerCase() === 'typography';
  }

  function checkSpacing() {
    return title.value.toLowerCase() === 'spacing';
  }

  function checkScoreCard() {
    return title.value.toLowerCase() === 'score card component';
  }

  const groups = reactive(colorGroup.groups);
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <ColorCard v-if="checkColor()" :groups="groups"></ColorCard>
    <GradientCard v-else-if="checkGradient()" :groups="groups"></GradientCard>
    <TypographyCard
      v-else-if="checkTypography()"
      :groups="groups"
    ></TypographyCard>
    <SpacingCard v-else-if="checkSpacing()" :groups="groups"></SpacingCard>
    <ScoreCard v-else-if="checkScoreCard()"></ScoreCard>
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
