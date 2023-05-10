<template>
  <footer>
    <p>
      Learning Resources, a Vue Practice App -
      <a href="https://tyrnisarkka.netlify.app/">Tyrni Särkkä</a> 2023
    </p>
  </footer>
</template>

<style scoped>
footer {
  width: 100%;
  height: 1.5rem;
  background-color: #2f3847;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  bottom: 0;
}
p {
  color: white;
  padding-bottom: 0.2rem;
  font-size: 0.8rem;
  letter-spacing: 1px;
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
