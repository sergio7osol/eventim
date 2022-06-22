<template>
    <h1>Detail</h1>
    <p>ID: {{ $route.params.id }}</p>
    <p>Description: {{ $route.params.desc }}</p>
</template>

<script setup>
    const route = useRoute();

    console.log(route.params);
</script>