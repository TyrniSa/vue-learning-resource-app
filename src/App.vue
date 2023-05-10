<template>
  <TheHeader/>
  <StoredResources :resources="storedResources" />
  <TheFooter/>
</template>

<script>
import TheFooter from './components/layouts/TheFooter.vue';
import TheHeader from './components/layouts/TheHeader.vue';
import StoredResources from './components/learning-resources/StoredResources.vue';


export default {
  components: {
    StoredResources,
    TheHeader,
    TheFooter
  },
  data() {
    return {
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Vue guide',
          description: 'Official Vue.js documentation',
          link: 'https://vuejs.org/',
        },
        {
          id: 'google',
          title: 'Google',
          description:
            'Because every developer needs to learn how to google. 😉',
          link: 'https://www.google.com/',
        },
      ],
    };
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
  background-color: rgba(231, 161, 23, 0.1)
}
h1 {
  font-family: 'Bebas Neue', sans-serif;
}
/* h2,
h3 {
  font-family: 'Lato', sans-serif;
} */
</style>
