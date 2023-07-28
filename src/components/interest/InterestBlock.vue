<template>
  <li>
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Remove</button>
      </header>
    </div>
    <p>{{ description }}</p>
    <nav>
      <a :href="link">Learn more...</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    link: String,
  },
};
</script>

<!-- These styles are specific to the InterestBlock component -->
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
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>
