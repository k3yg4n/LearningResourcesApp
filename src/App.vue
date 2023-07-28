<template>
  <the-header :title="appTitle"></the-header>
  <the-interests></the-interests>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheInterests from './components/interest/TheInterests.vue';

export default {
  components: {
    'the-header': TheHeader,
    'the-interests': TheInterests,
  },
  data() {
    return {
      appTitle: 'Keegan Liu - More About Me',
    };
  },
  methods: {
    removeInterest(interestIdToDel) {
      this.StoredInterests = this.StoredInterests.filter(
        (interest) => interest.id !== interestIdToDel
      );
    },
  },
};
</script>

<!-- Application wide styling -->
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
