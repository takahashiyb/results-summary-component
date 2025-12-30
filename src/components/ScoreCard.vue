<script setup></script>

<template>
  <section>
    <h2>Your Result</h2>
    <div class="score-circle">
      <p class="score-actual">76</p>
      <p class="score-total">of 100</p>
    </div>
    <div class="text-content">
      <p class="rating">Great</p>
      <p class="comment">
        You scored higher than 65% of the people who have taken these tests.
      </p>
    </div>
  </section>
</template>

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-0400);

    place-items: center;
    background: linear-gradient(var(--gradient-2));
    text-align: center;
    padding: var(--spacing-0400) 4em 5em 4em;
    border-radius: 0 0 32px 32px;
  }

  h2 {
    font: var(--font-preset-4);
    color: hsl(var(--navy-200-color));
  }

  .score-circle {
    align-content: center;

    height: 200px;
    aspect-ratio: 1;
    background: linear-gradient(to bottom, var(--gradient-1));

    border-radius: 50%;
  }

  .score-actual {
    font: var(--font-preset-1);
    color: hsl(var(--white-color));
  }

  .score-total {
    font: var(--font-preset-5-b);
    color: hsl(var(--navy-200-color));
  }

  .text-content {
    display: inherit;
    flex-direction: inherit;
    gap: var(--spacing-0200);
  }

  .rating {
    font: var(--font-preset-3);
    color: hsl(var(--white-color));
  }

  .comment {
    font: var(--font-preset-5-m);
    color: hsl(var(--navy-200-color));
  }

  @media (min-width: 43.75em) {
    section {
      border-radius: 32px;
      padding: 5em 4em;
      max-width: 368px;
    }
  }
</style>
