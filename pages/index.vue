<script setup>
    const { data: events } = await useAsyncData('events', () => $fetch('https://www.eventim-light.com/de/a/5da03c56503ca200015df6cb/api/event'));
</script>

<template>
    <div class="event-list mt-4"> 
        <div class="col sm:col-6 md:col-4" v-for="(event, index) in events">
            <EventCard 
                :id="event.id"
                :title="event.title" 
                :copyright="event.image.copyright"
                :start="event.start" 
                :location="`${event.venue.street}, ${event.venue.city}`"
                :minPrice="event.minPrice.value" />
        </div>
    </div>
</template>

<style scoped lang="scss">
    @use 'primeflex/primeflex';

    .event-list {
        @include primeflex.styleclass('grid');
    }
</style>

