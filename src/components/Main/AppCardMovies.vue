<script>
import { store } from '../../store'
export default {
    name: 'AppCardMovies',
    data() {
        return {
            store,
        }
    }
}

</script>

<template>
    <div class="text-white d-flex" v-for="movie in store.movies">

        <h5><em>Titolo: </em>{{ movie.title }} |</h5>
        <h6><em> Titolo originale: </em>{{ movie.original_title }} |</h6>
        <p class="ms-2"><em> Lingua: </em>{{ movie.original_language }} |</p>
        <div class="ms-3"><em> Voto: </em>{{ movie.vote_average }}</div>
        <hr>

    </div>
</template>

<style lang="scss" scoped>
em {
    color: orange;
}
</style>
