<template>
  <div v-if="event">
    <h2>{{ event.title }}</h2>
    <p>{{event.time}} on {{event.date}} @ {{event.location}}</p>
    <p>{{ event.description }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import EventService from "@/services/EventService.js";

const event = ref(null);
const props = defineProps({
  id: {required: true}
})

onMounted(() => {
  EventService.getEvent(props.id)
      .then((response) => {
        event.value = response.data
      })
      .catch((error) => {
        console.log(error)
      })
})
</script>

<style scoped>

</style>