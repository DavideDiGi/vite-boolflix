<script>
import { store } from '../../store'
export default {
    name: 'AppCardMovies',
    data() {
        return {
            store,
        }
    },
    methods: {
        generateFlag(country) {

            switch (country) {
                case 'en':
                    country = 'uk'
                    break;
                case 'es':
                    country = 'sp'
                    break;
                case 'pt':
                    country = 'po'
                    break;
                case 'de':
                    country = 'gm'
                    break;
                case 'ru':
                    country = 'rs'
                    break;
            }

            let flag = `https://www.worldometers.info//img/flags/small/tn_${country}-flag.gif`;

            if (country != 'uk' &&
                country != 'it' &&
                country != 'ja' &&
                country != 'gm' &&
                country != 'po' &&
                country != 'sp' &&
                country != 'fr' &&
                country != 'pl' &&
                country != 'rs' &&
                country != 'hu'
            ) {
                flag = 'src/assets/imgnotfound.png'
            }
            return flag;

        },
        urlsAssemble(urlEnd) {
            const urlStart = 'https://image.tmdb.org/t/p/';
            const urlWidth = 'w342';

            let Alltogether = urlStart + urlWidth + urlEnd;

            return Alltogether;
        }

    }
}

</script>

<template>

    <div class="text-white d-flex" v-for="movie in store.movies">
        <h5><em>Titolo Film: </em>{{ movie.title }} |</h5>
        <h6><em> Titolo originale: </em>{{ movie.original_title }} |</h6>
        <img class="poster" :src="urlsAssemble(movie.poster_path)" :alt="movie.title">
        <p class="ms-2"><em> Lingua: </em>{{ movie.original_language }} </p>
        <img class="ms-2 flag" :src="generateFlag(movie.original_language)" alt="ooo">
        <div class="ms-3">|<em> Voto: </em>{{ movie.vote_average }}</div>
        <hr>
    </div>

    <div class="text-white d-flex" v-for="serie in store.series">
        <h5><em>Titolo Serie-TV: </em>{{ serie.name }} |</h5>
        <h6><em> Titolo originale: </em>{{ serie.original_name }} |</h6>
        <img class="poster" :src="urlsAssemble(serie.poster_path)" :alt="serie.name">
        <p class="ms-2"><em> Lingua: </em>{{ serie.original_language }} </p>
        <img class="ms-2 flag" :src="generateFlag(serie.original_language)" alt="ooo">
        <div class="ms-3">|<em> Voto: </em>{{ serie.vote_average }}</div>
    </div>

</template>

<style lang="scss" scoped>
em {
    color: orange;
}

.flag {
    width: 20px;
    height: 20px;
    object-fit: contain;
}

.poster {
    width: 200px;
    height: 200px;
    object-fit: contain;
}
</style>
