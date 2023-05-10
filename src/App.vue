<template>
  <TheHeader />
  <TheResources />
  <TheFooter />
</template>

<script>
import TheFooter from './components/layouts/TheFooter.vue';
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';

export default {
  components: {
    TheHeader,
    TheResources,
    TheFooter,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Lato:wght@100;400;700&family=Roboto:ital,wght@0,100;0,400;1,100;1,400&display=swap');

* {
  box-sizing: border-box;
}
html {
  font-family: 'Roboto', sans-serif;
  color: #222832;
}
body {
  margin: 0;
  background-color: rgba(231, 161, 23, 0.1);
}
h1 {
  font-family: 'Bebas Neue', sans-serif;
}
/* h2,
h3 {
  font-family: 'Lato', sans-serif;
} */
</style>
