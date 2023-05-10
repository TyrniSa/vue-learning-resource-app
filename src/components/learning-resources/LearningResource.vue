<template>
  <li>
    <base-card>
      <header>
        <h3>{{ title }}</h3>
        <base-button mode="flat">Delete</base-button>
      </header>
      <p>{{ description }}</p>
      <nav>
        <a :href="link" target="_blank">View resource</a>
      </nav>
    </base-card>
  </li>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
    },
    description: {
      type: String,
    },
    link: {
      type: String,
    },
  },
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
  font-weight: 500;
}
p {
  margin: 0.5rem 0;
  font-weight: 400;
}
a {
  text-decoration: none;
  color: #c57f1e;
}
a:hover,
a:active {
  color: #e7a117;
}
</style>
