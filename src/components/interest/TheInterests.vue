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
  <component :is="selectedTab"></component>
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
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
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
