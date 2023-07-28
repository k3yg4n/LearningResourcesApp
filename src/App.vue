<template>
  <the-header :title="appTitle"></the-header>
  <stored-interests
    :interests="storedInterests"
    @remove-interest="removeInterest"
  ></stored-interests>
</template>

<script>
import StoredInterests from './components/interest/StoredInterests.vue';
import TheHeader from './components/layouts/TheHeader.vue';

export default {
  components: {
    'stored-interests': StoredInterests,
    'the-header': TheHeader,
  },
  data() {
    return {
      appTitle: 'Keegan Liu - More About Me',
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
