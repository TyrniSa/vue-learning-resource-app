<template>
  <button :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['mode'],
};
</script>

<style>
button {
  padding: 0.75rem 1.5rem;
  font-family: 'Bebas Neue', sans-serif;
  letter-spacing: 1px;
  font-size: 1rem;
  background-color: #E7A117;
  border: none;
  color: #222832;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #C57F1E;
  border-color: #C57F1E;
  color: #fff;
}

.flat {
  background-color: transparent;
  color: #c57f1e;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #C57F1E;
  color: #fff;
  border: none;
}
</style>
