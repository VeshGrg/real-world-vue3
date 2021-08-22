<template>
    <div v-if="event">
     <span>@ {{ event.time}} on {{ event.date }}</span>
    <h4> {{ event.title}}</h4>
    <h3>{{ event.description }}</h3>
   </div>
</template>

<script>
import EventService from '@/services/EventService.js';
export default{
    props: ['id'],
    data(){
        return {
            event: null
            }
    },
    created(){
        EventService.getEvent(this.id)
        .then(response => { 
            this.event = response.data
        })
        .catch(error => {
            console.log(error)
        })
    }
}
</script>
