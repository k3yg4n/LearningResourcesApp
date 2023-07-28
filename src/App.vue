<template>
  <ul>
    <interest-block
      v-for="int in storedInterests"
      :key="int.id"
      :title="int.title"
      :description="int.description"
      :link="int.link"
    ></interest-block>
  </ul>
</template>

<script>
import Interest from './components/interest/InterestBlock.vue';
export default {
  components: {
    'interest-block': Interest,
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
