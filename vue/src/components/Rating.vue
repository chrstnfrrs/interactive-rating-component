<template>
  <main class="rating-card">
    <RatingResponse v-if="rating" :rating="rating" />
    <RatingSurvey v-else :setRating="setRating" />
  </main>
</template>

<script setup>
import { ref } from "vue";
import RatingResponse from "./RatingResponse.vue";
import RatingSurvey from "./RatingSurvey.vue";

const rating = ref(undefined);
const setRating = (num) => {
  rating.value = num;
};
</script>

<style lang="scss">
.rating-card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  border-radius: 1.875rem;
  padding: 2rem;
  background: linear-gradient(
    0deg,
    hsl(215, 24%, 12%, 100%) 0%,
    hsl(215, 20%, 17%, 100%) 100%
  );
  max-width: 25.75rem;
  height: 26rem;
  @media only screen and (max-width: 660px) {
    padding: 1.5rem;
    max-width: 20.4375rem;
    height: 22.5rem;
  }
}
</style>
