<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['type', 'mode'],
};
</script>

<style>
button {
  padding: 0.75rem 1.5rem;
  font-family: 'Bebas Neue', sans-serif;
  letter-spacing: 1px;
  font-size: 1rem;
  background-color: #c57f1e;
  border: 1px solid #c57f1e;
  color: #222832;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #754c13;
  border-color: #754c13;
  color: #fff;
}

.flat {
  background-color: transparent;
  color: #c57f1e;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #e7a117;
  color: #fff;
}
</style>
