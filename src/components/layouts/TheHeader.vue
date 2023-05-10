<template>
  <header>
    <h1>Learning Resources App 📚</h1>
  </header>
</template>

<style scoped>
header {
  width: 100%;
  height: 5rem;
  background-color: #2f3847;
  display: flex;
  justify-content: center;
  align-items: center;
}
header h1 {
  color: white;
  margin: 0;
  font-weight: 700;
  font-size: 3.5rem;
  letter-spacing: 1px;
}
@media screen and (max-width: 650px) {
  header {
  height: 3rem;
}
header h1 {
  font-size: 2rem;
}
}
</style>
