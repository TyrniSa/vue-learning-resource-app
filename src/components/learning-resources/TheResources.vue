<template>
  <base-card id="linkCard">
    <base-button
      @click="setSelectedTab('storedResources')"
      :mode="storedButtonMode"
      >Stored Resources</base-button
    >
    <base-button @click="setSelectedTab('addResource')" :mode="addButtonMode"
      >Add Resource</base-button
    >
  </base-card>
  <KeepAlive>
    <component :is="selectedTab"></component>
  </KeepAlive>
</template>

<script>
import AddResource from './AddResource.vue';
import StoredResources from './StoredResources.vue';

export default {
  components: {
    StoredResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: 'storedResources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Vue guide',
          description: 'Official Vue.js documentation',
          link: 'https://vuejs.org/',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Because every developer has to learn how to google. 😉',
          link: 'https://www.google.com/',
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    };
  },
  computed: {
    storedButtonMode() {
      return this.selectedTab === 'storedResources' ? null : 'flat';
    },
    addButtonMode() {
      return this.selectedTab === 'addResource' ? null : 'flat';
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, desc, link) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: desc,
        link: link,
      };

      this.storedResources.push(newResource);
      this.selectedTab = 'storedResources';
    },
    removeResource(id){
      const index = this.storedResources.findIndex(res => res.id === id);
      this.storedResources.splice(index, 1);
    }
  },
};
</script>

<style scoped>
#linkCard {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
button {
  width: 50%;
  border-radius: 0%;
}
</style>
