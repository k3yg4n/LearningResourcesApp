<template>
  <stored-interests :interests="storedInterests"></stored-interests>
</template>

<script>
import StoredInterests from './components/interest/StoredInterests.vue';

export default {
  components: {
    'stored-interests': StoredInterests,
  },
  data() {
    return {
      storedInterests: [
        {
          id: 'favourite-album',
          title: 'My favourite album',
          description: 'This is my favourite album.',
          link: 'https://google.com',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google...',
          link: 'https://google.com',
        },
      ],
    };
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
