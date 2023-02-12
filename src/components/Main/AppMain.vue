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
    <div class="bg-dark">

        <h2>Film:</h2>
        <div class="card-container">
            <!-- <div class="card"> -->
            <AppCard v-for="movie in store.movies" :element="movie" />
            <!-- </div> -->
        </div>

        <!-- <h2>Serie TV:</h2>
        <div>
            <AppCard v-for="serie in store.series" :element="serie" />
        </div> -->

    </div>
</template>

<style lang="scss" scoped>
.bg-dark {
    height: calc(100% - 70px);
    display: flex;

    .card-container {
        // width: 20%;
        height: 100%;

        .card {
            height: 100%;
            // float: left;
            // min-height: 512px;
            // background-color: black;
            // border: 1px solid white;


        }
    }
}
</style>
