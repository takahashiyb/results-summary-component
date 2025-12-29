<script setup>
import { ref, reactive, defineProps } from "vue";

import ColorCard from "@/design-system/ColorCard.vue";
import GradientCard from "./GradientCard.vue";

const props = defineProps({
  object: Object,
});

const colorGroup = reactive(props.object);

const title = ref(colorGroup.category);

const isColor = checkColor();

function checkColor() {
  return title.value.toLowerCase() === "colors";
}

const isGradient = checkGradient();

function checkGradient() {
  return title.value.toLowerCase() === "gradients";
}

const groups = reactive(colorGroup.groups);
</script>

<template>
  <h1>{{ title }}</h1>
  <ColorCard v-if="isColor" :groups="groups"></ColorCard>
  <GradientCard v-if="isGradient" :groups="groups"></GradientCard>
</template>

<style scoped>
h1 {
  text-transform: capitalize;
  padding-top: 72px;
}
</style>
