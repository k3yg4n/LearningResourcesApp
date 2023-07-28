<template>
  <li>
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete Interest</button>
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
