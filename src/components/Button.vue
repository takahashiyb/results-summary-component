<script setup></script>

<template>
  <button>Continue</button>
</template>

<style scoped>
  button {
    width: 288px;
    height: 56px;

    background: hsl(var(--navy-950-color));
    color: hsl(var(--white-color));
    font: var(--font-preset-5-b);

    border: none;
    border-radius: 9em;
  }

  button:hover {
    background: linear-gradient(var(--gradient-2));
  }
</style>
