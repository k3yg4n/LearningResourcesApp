<template>
  <ul>
    <interest-block
      v-for="int in interests"
      :key="int.id"
      :title="int.title"
      :description="int.description"
      :link="int.link"
    ></interest-block>
  </ul>
</template>

<script>
import InterestBlock from './InterestBlock.vue';

export default {
  props: {
    interests: Array,
  },
  components: {
    'interest-block': InterestBlock,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
