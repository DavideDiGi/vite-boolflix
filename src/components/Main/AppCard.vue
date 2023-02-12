<script>
import { store } from '../../store'
export default {
    name: 'AppCard',
    props: {
        element: Object,
    },
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
        },
        voteChanger() {
            let changedVote = this.element.vote_average;
            changedVote = changedVote / 2;
            changedVote = Math.ceil(changedVote);
            return changedVote;
        }
    }
}

</script>

<template>

    <h4><em>Titolo: </em>{{ element.title }} || {{ element.name }} |</h4>
    <h5><em> Titolo originale: </em>{{ element.original_title }} || {{ element.original_name }} |</h5>
    <img class="poster" :src="urlsAssemble(element.poster_path)" :alt="element.title">
    <br>
    <br>
    <span class="ms-2"><em> Lingua: </em>{{ element.original_language }} </span>
    <img class="ms-1 flag" :src="generateFlag(element.original_language)" alt="flag">
    <span><em> Voto: </em></span>
    <span v-for="star in voteChanger()"> &#9733; </span>
    <span v-for="star in (5 - voteChanger())"> &#9734; </span>

    <hr>

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
    width: 100%;
    // height: 100%;
}
</style>
