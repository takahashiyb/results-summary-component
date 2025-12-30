<script setup>
  // import DesignSystem from '@/design-system/DesignSystem.vue';
  import Button from './components/Button.vue';
  import ScoreCard from './components/ScoreCard.vue';
  import SingleScore from './components/SingleScore.vue';

  import list from '../data/data.json';
</script>

<template>
  <!-- <DesignSystem></DesignSystem> -->
  <div class="grid">
    <section class="container__score-card">
      <ScoreCard></ScoreCard>
    </section>
    <section class="container__score-list">
      <p>Summary</p>
      <SingleScore
        v-for="score in list"
        :key="score.category"
        :data="score"
      ></SingleScore>
    </section>
    <section class="container__continue">
      <Button></Button>
    </section>
  </div>
</template>

<style scoped>
  .grid {
    display: grid;
    justify-items: center;

    gap: var(--spacing-0300);
    max-width: 736px;

    margin-inline: auto;

    border-radius: 32px;

    box-shadow: 20px 20px 15px hsl(var(--blue-050-color));

    padding-bottom: var(--spacing-0400);
  }

  p {
    padding-bottom: var(--spacing-0100);

    font: var(--font-preset-4);
  }

  .container__score-list {
    display: grid;
    width: 100%;
    justify-content: stretch;
    gap: var(--spacing-0200);

    padding-inline: var(--spacing-0400);
  }

  @media (min-width: 43.75em) {
    .grid {
      grid-template-columns: 1fr 1fr;
      grid-template-rows: min-content 1fr;

      padding-bottom: 0;
    }

    .container__score-card {
      grid-column: 1;
      grid-row: 1/3;
    }

    .container__score-list {
      grid-column: 2;
      grid-row: 1/2;

      align-self: flex-start;

      padding-top: 5em;
    }

    .container__continue {
      grid-column: 2;
      grid-row: 2/3;

      align-self: flex-start;
    }
  }
</style>
