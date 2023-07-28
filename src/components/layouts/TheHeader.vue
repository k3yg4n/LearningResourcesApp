<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  props: {
    title: String,
  },
};
</script>

<style scoped>
header {
  width: 100%;
  height: 8rem;
  background-color: #79adea;
  display: flex;
  justify-content: center;
  align-items: center;
}

header h1 {
  color: rgb(45, 7, 7);
  margin: 0;
}
</style>
