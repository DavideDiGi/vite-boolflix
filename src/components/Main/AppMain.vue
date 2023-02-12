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
    <div class="bg-success">

        <h2>film</h2>
        <AppCard v-for="movie in store.movies" :element="movie" />

        <h2>serie</h2>
        <AppCard v-for="serie in store.series" :element="serie" />

    </div>
</template>

<style lang="scss" scoped>

</style>
