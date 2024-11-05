<!-- 1.6.Add a new edit button in the edit component, when click just move to the details page and show the flash message INSIDE the event-detail component, the message should state that the data has been updated -->
<template>
  <div>
    <!-- Other template code -->
    <button @click="navigateToDetails">Edit</button>
  </div>
</template>

<script lang="ts">
export default {
  methods: {
    navigateToDetails() {
      this.$router.push({ name: 'EventDetail', params: { id: this.$route.params.id, updated: 'true' } });
    },
  },
};
</script>
