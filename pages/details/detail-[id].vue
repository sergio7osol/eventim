<script setup>
    const { title, date, time, location, price } = useRoute().params;
</script>

<template>
    <div class="card">
        <table class="details-table mt-4">
            <tr>
                <th class="details-table__cell">Title:</th>
                <td class="details-table__cell">{{ title }}</td>
            </tr>
            <tr>
                <th class="details-table__cell">Date:</th>
                <td class="details-table__cell">{{ date }}</td>
            </tr>
            <tr>
                <th class="details-table__cell">Time:</th>
                <td class="details-table__cell">{{ time }}</td>
            </tr>
            <tr>
                <th class="details-table__cell">Location:</th>
                <td class="details-table__cell">{{ location }}</td>
            </tr>
            <tr>
                <th class="details-table__cell">Price:</th>
                <td class="details-table__cell">{{ price }}</td>
            </tr>
        </table>
    </div>
</template>

<style scoped lang="scss">
    .details-table {
        text-align: left;
        &__cell {
            padding: .5rem 1rem;
        }
    }
</style>