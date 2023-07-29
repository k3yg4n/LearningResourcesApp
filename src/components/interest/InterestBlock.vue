<template>
  <li>
    <base-card>
      <header>
        <h3>{{ title }}</h3>
        <base-button mode="flat" @click="removeInterest(id)">
          Remove
        </base-button>
      </header>
      <p>{{ description }}</p>
      <nav>
        <a :href="link">Learn more...</a>
      </nav>
    </base-card>
  </li>
</template>

<script>
export default {
  props: {
    id: String,
    title: String,
    description: String,
    link: String,
  },
  inject: ['removeInterest'],
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
  color: #349bf6;
}

a:hover,
a:active {
  color: #53a6e7;
}
</style>
