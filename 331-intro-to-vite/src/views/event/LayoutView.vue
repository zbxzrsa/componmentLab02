<script setup lang="ts">
import { useEventStore } from 'c:/Users/zhang/lab3-Vue-Router/331-intro-to-vite/src/stores/event'
import { storeToRefs } from 'pinia'
// import { ref, onMounted } from 'vue'
// import { type Event } from 'c:/Users/zhang/lab3-Vue-Router/331-intro-to-vite/src/types'
// import EventService from 'c:/Users/zhang/lab3-Vue-Router/331-intro-to-vite/src/services/EventService'
// import { useRouter } from 'vue-router'

// const event = ref<Event | null>(null)
// const props = defineProps({
//   id: {
//     type: String,
//     required: true
//   }
// })
// const router = useRouter()
const store = useEventStore()
const { event } = storeToRefs(store)

// onMounted(() => {
//   EventService.getEvent(parseInt(props.id))
//     .then((response) => {
//       event.value = response.data
//     })
//     .catch((error) => {
//       if (error.respose && error.response.status === 404) {
//         router.push({
//           name: '404-resource-view',
//           params: { resource: 'event' }
//         })
//       } else {
//         router.push({ name: 'network-error-view' })
//       }
//     })
// })
</script>

<template>
  <div v-if="event">
    <h1>{{ event.title }}</h1>
    <nav>
      <RouterLink :to="{ name: 'event-detail-view' }">Details</RouterLink>
      |
      <RouterLink :to="{ name: 'event-register-view' }">Register</RouterLink>
      |
      <RouterLink :to="{ name: 'event-edit-view' }">Edit</RouterLink>
    </nav>
    <RouterView :event="event" />
  </div>
</template>
