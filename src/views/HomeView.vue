<script setup>
import EventCard from "@/components/EventCard.vue";
import {onMounted, ref} from "vue";
import EventService from "@/services/EventService.js";

const events = ref(null)

onMounted(() => {
  EventService.getEvents()
  .then((response) => {
    events.value = response.data
  })
  .catch((error) => {
    console.log(error)
  })

})
</script>

<template>
  <div class="events">
    <EventCard  v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<style scoped>
  .events{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap:12px;
  }
</style>
