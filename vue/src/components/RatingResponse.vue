<template>
  <div class="rating-response__illustration-container">
    <figure>
      <img
        class="rating-response__illustration"
        src="../assets/illustration-thank-you.svg"
        alt=""
      />
    </figure>
  </div>
  <p class="rating-response__rating">You selected {{ rating }} out of 5</p>
  <h1 class="rating-response__heading">Thank you!</h1>
  <p class="rating-response__text">
    We appreciate you taking the time to give a rating. If you ever need more
    support, don’t hesitate to get in touch!
  </p>
</template>

<script setup>
import { defineProps, toRefs } from "vue";

const props = defineProps({
  rating: String,
});

const { rating } = toRefs(props);
</script>

<style lang="scss">
.rating-response {
  &__illustration-container {
    display: flex;
    justify-content: center;
    user-select: none;
    margin-bottom: 2rem;
    @media only screen and (max-width: 660px) {
      margin-bottom: 1.5rem;
    }
  }
  &__illustration {
    width: 10.125rem;
    height: 6.75rem;
    @media only screen and (max-width: 660px) {
      width: 9rem;
      height: 6rem;
    }
  }
  &__rating {
    width: fit-content;
    margin: 0 auto;
    color: var(--orange);
    background-color: var(--dark-blue);
    border-radius: 22.5px;
    font-size: 0.9375rem;
    line-height: 1.5;
    margin-bottom: 2rem;
    user-select: none;
    padding: 0.25rem 1.25rem;
    @media only screen and (max-width: 660px) {
      padding: 0.25rem 0.75rem;
      margin-bottom: 1.5rem;
    }
  }
  &__heading {
    text-align: center;
    color: white;
    font-size: 1.875rem;
    font-weight: 700;
    margin-bottom: 1rem;
    @media only screen and (max-width: 660px) {
      margin-bottom: 0.675rem;
    }
  }
  &__text {
    text-align: center;
    color: var(--light-grey);
    font-size: 0.9375rem;
    line-height: 1.5;
    word-spacing: 1px;
  }
}
</style>
