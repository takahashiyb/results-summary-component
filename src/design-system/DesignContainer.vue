<script setup>
  
  import { ref, reactive, defineProps } from 'vue'
  
  import ColorCard from "@/design-system/ColorCard.vue";

  const props = defineProps({
    object: Object
  })

  const colorGroup = reactive(props.object)

  const title = ref(colorGroup.category)

  const isColor = checkColor()

  const groups = reactive(colorGroup.groups)

  function checkColor() {
    return title.value.toLowerCase() === "colors"
  }

</script>

<template>
  <h1>{{title}}</h1>
  <slot>
    <ColorCard v-if="isColor" :groups="groups"></ColorCard>
  </slot>
</template>

<style scoped>
  h1 {
    text-transform: capitalize;
  }
</style>
