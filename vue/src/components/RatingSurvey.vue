<template>
  <figure class="rating-survey__icon-container">
    <img class="rating-survey__icon" src="../assets/icon-star.svg" alt="" />
  </figure>
  <h1 class="rating-survey__heading">How did we do?</h1>
  <p class="rating-survey__text">
    Please let us know how we did with your support request. All feedback is
    appreciated to help us improve our offering!
  </p>
  <div class="rating-survey__rating_row">
    <div
      v-for="i in 5"
      :key="i"
      :class="getRatingItemClasses(i)"
      @click="setSelection(i)"
    >
      {{ i }}
    </div>
  </div>
  <button class="rating-survey__button" @click="submitSelection">SUBMIT</button>
</template>

<script setup>
import { defineProps, ref, toRefs } from "vue";
const props = defineProps({
  setRating: Function,
});

const selection = ref(undefined);

const setSelection = (i) => {
  selection.value = i;
};
const { setRating } = toRefs(props);

const submitSelection = () => {
  setRating.value(String(selection.value));
};

const getRatingItemClasses = (i) =>
  selection.value === i
    ? "rating-survey__rating_item rating-survey__rating_item--active"
    : "rating-survey__rating_item";
</script>

<style lang="scss">
.rating-survey {
  &__icon-container {
    user-select: none;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    background-color: var(--dark-blue);
    width: 3rem;
    height: 3rem;
    @media only screen and (max-width: 660px) {
      width: 2.25rem;
      height: 2.25rem;
    }
  }
  &__icon {
    width: 1rem;
    height: 1rem;
    @media only screen and (max-width: 660px) {
      width: 0.875rem;
      height: 0.875rem;
    }
  }
  &__heading {
    color: white;
    font-size: 1.875rem;
    font-weight: 700;
    margin-top: 2rem;
    margin-bottom: 1rem;
    @media only screen and (max-width: 660px) {
      margin-top: 1rem;
      margin-bottom: 0.675rem;
    }
  }
  &__text {
    color: var(--light-grey);
    line-height: 1.5;
    margin-bottom: 1.5rem;
    font-size: 0.9375rem;
    @media only screen and (max-width: 660px) {
      font-size: 0.875rem;
    }
  }
  &__rating_row {
    display: flex;
    width: 100%;
    justify-content: space-between;
    margin-bottom: 2rem;
    @media only screen and (max-width: 660px) {
      margin-bottom: 1.5rem;
    }
  }
  &__rating_item {
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    background-color: var(--dark-blue);
    color: var(--medium-grey);
    user-select: none;
    font-weight: 700;
    height: 3.125rem;
    width: 3.125rem;
    @media only screen and (max-width: 660px) {
      height: 2.625rem;
      width: 2.625rem;
    }
    &:hover {
      background-color: var(--orange);
      color: white;
    }
    &--active {
      background-color: var(--medium-grey);
      color: white;
    }
  }
  &__button {
    cursor: pointer;
    border-radius: 22.5px;
    border: none;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 0.875rem;
    background-color: var(--orange);
    color: white;
    &:hover {
      color: var(--orange);
      background-color: white;
    }
  }
}
</style>
