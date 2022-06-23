import { NuxtModule } from '@nuxt/schema';
<script setup lang="ts">
    const props = defineProps<{
        id: string,
        copyright: string,
        title: string,
        start: string,
        location: string,
        minPrice: string
    }>();

    const dateTime = new Date(props.start as string);
    const date = dateTime.getDate();
    const month = ("0" + (dateTime.getMonth() + 1)).slice(-2);
    const year = dateTime.getFullYear();
    const hours = dateTime.getHours();
    const minutes = ("0" + dateTime.getMinutes()).slice(-2);

    const details = {
        id: props.id,
        title: props.title,
        date: `${date}.${month}.${year}`, 
        time: `${hours}:${minutes}`,
        location: props.location,
        price: `from ${props.minPrice}`
    };
</script>

<template>
    <Card>
        <template #header>
            <picture>
                <source srcset="/images/card-img-250.webp" media="(min-width: 1024px)" type="image/webp" />
                <img class="event-card__pic" 
                    src="/images/card-img.png" 
                    width="250"
                    height="250" 
                    :alt="title" 
                    loading="lazy" />
            </picture>
        </template>
        <template #title>
            {{ title }} 
        </template>
        <template #content>
            <span class="event-card__copyright">Image: {{ copyright }}</span>
            <div class="event-card__date-time">
                <span class="event-card__date">
                    <i class="pi pi-calendar"></i> {{ `${date}.${month}.${year}` }}
                </span>
                <span class="event-card__time">
                    <i class="pi pi-clock"></i> {{ `${hours}:${minutes}` }}
                </span>
            </div>
            <div class="event-card__location"><i class="pi pi-map-marker"></i> {{ location }}</div>
        </template>
        <template #footer>
            <nuxt-link :to="{ name: 'details-detail-id', params: { ...details } }">
                <Button icon="pi pi-euro" iconPos="right" :label="`from ${minPrice}`" />
            </nuxt-link>
        </template>
    </Card>
</template>

<style>
    /* override */
    a {
        text-decoration: none;
    }
    .p-card-body {
        position: relative;
    }
    .p-card-footer {
        display: flex;
        justify-content: flex-end;
    }
</style>
<style scoped lang="scss"> 
@use 'primeflex/primeflex';
.event-card {
    &__pic {
        max-width: 100%;
        max-height: 12rem;
        object-fit: cover;
    }
    &__copyright { 
        @include primeflex.styleclass('text-xs');
        position: absolute;
        top: 0;
    }
    &__date-time {
        @include primeflex.styleclass('mb-2');
    }
    &__date {
        @include primeflex.styleclass('mr-3');
    }
}
</style>