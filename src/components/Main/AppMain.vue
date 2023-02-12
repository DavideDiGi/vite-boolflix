<script>
import { store } from '../../store';
import AppCardMovies from './AppCardMovies.vue';

export default {
    name: "AppMain",
    data() {
        return {
            store
        };
    },
    components: {
        AppCardMovies,
    }
}

</script>

<template>
    <div class="bg-success">
        <AppCardMovies />
    </div>
</template>

<style lang="scss" scoped>

</style>
