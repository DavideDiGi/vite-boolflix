<script>
import { store } from '../../store';
import AppCard from './AppCard.vue';

export default {
    name: "AppMain",
    data() {
        return {
            store
        };
    },
    components: {
        AppCard,
    }
}

</script>

<template>
    <main class="bg-dark">
        <!-- FILM -->
        <h2 class="text-white pt-3 ps-4 w-100">Film trovati:</h2>

        <div class="card-container mt-3">
            <AppCard v-for="movie in store.movies" :element="movie" />
        </div>
        <!-- SERIE TV -->
        <h2 class="text-white pt-3 ps-4 w-100">Serie TV trovate:</h2>

        <div class="card-container mt-3">
            <AppCard v-for="serie in store.series" :element="serie" />
        </div>

    </main>
</template>

<style lang="scss" >
main {
    .card-container {
        min-height: 513px;
        display: flex;
        overflow-x: auto;
        position: relative;
    }
}
</style>
