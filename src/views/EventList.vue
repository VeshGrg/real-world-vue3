<template>
<h1>Events for the day</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event"/>
    <div ></div>
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue";
import axios from "axios";
import EventService from "@/services/EventService.js";

export default {
  name: "EventList",
  components: {
    EventCard,
  }, 
  data(){
    return {
      events: null
      }
    },
    created(){
      EventService.getEvents()
      .then(response => { 
        this.events = response.data
      })
      .catch(error => {
        console.log(error)
      })
    }
};
</script>

<style scoped>
  .events{
    display: flex;
    flex-direction: column;
    align-items:center;
  }
</style>


