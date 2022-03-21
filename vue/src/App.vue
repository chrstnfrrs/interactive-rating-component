<template>
  <Rating />
</template>

<script>
import Rating from "./components/Rating.vue";

export default {
  name: "App",
  components: {
    Rating,
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Overpass:wght@400;700&display=swap");

html {
  font-family: "Overpass", Helvetica, Arial, sans-serif;
  src: local("Overpass"), local("Overpass"),
    url(https://fonts.googleapis.com/css2?family=Overpass:wght@400;700)
      format("woff2");
  font-display: swap;
}

:root {
  --orange: hsl(25, 97%, 53%);
  --light-grey: hsl(216, 12%, 63%);
  --dark-blue: hsl(213, 19%, 18%);
  --medium-grey: hsl(217, 12%, 54%);
}

* {
  box-sizing: border-box;
}

body,
h1,
p,
figure {
  margin: 0;
}

#app {
  background-color: hsl(218, 11%, 8%);
  min-height: 100vh;
  min-width: 100vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
