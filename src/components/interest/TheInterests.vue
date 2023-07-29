<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-interests')"
      :mode="storedInterestsButtonMode"
      >Stored Interests</base-button
    >
    <base-button
      @click="setSelectedTab('add-interest')"
      :mode="addInterestButtonMode"
      >Add New Interests</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab" @add-new-interest="addNewInterest"></component>
  </keep-alive>
</template>

<script>
import StoredInterests from './StoredInterests.vue';
import AddInterest from './AddInterest.vue';

export default {
  components: {
    'stored-interests': StoredInterests,
    'add-interest': AddInterest,
  },
  data() {
    return {
      selectedTab: 'stored-interests',
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
  provide() {
    return {
      interests: this.storedInterests,
      addInterest: this.addNewInterest,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addNewInterest(newTitle, newDesc, newLink) {
      const newInterest = {
        id: new Date().toISOString(),
        title: newTitle,
        description: newDesc,
        link: newLink,
      };
      this.storedInterests.unshift(newInterest);
      this.selectedTab = 'stored-interests';
    },
  },
  computed: {
    storedInterestsButtonMode() {
      return this.selectedTab === 'stored-interests' ? null : 'flat';
    },
    addInterestButtonMode() {
      return this.selectedTab === 'add-interest' ? null : 'flat';
    },
  },
};
</script>
