<template>
<router-link class='event-link' :to="{ name: 'EventDetail', params: {id: event.id} }">
  <div class="event-card">
   <span>@ {{ event.time}} on {{ event.date }}</span>
   <h4> {{ event.title}}</h4>
   <h3>{{ event.description }}</h3>
    </div>
</router-link>
</template>

<script>
export default {
  name: "EventCard",
  props: {
    event: Object
  }
};
</script>

<style scoped>
  .event-card{
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid grey;
    margin-bottom: 18px;
  }
  .event-card:hover{
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0 , 0, 0.2);
  }
  .event-link{
    color: grey;
    text-decoration:none;
  }
</style>
