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

    <div class="card text-white ">
        <!-- copertina film -->
        <img class=" poster" :src="urlsAssemble(element.poster_path)" :alt="element.title">
        <!-- scheda overlay con informazioni -->
        <div class="overlay px-3 pt-4">

            <div><strong>Titolo: </strong>{{ element.title }} {{ element.name }}</div>
            <div><strong>Titolo originale: </strong>{{ element.original_title }} {{ element.original_name }}</div>
            <span><strong> Lingua: </strong>{{ element.original_language }} </span>
            <img class="ms-1 flag" :src="generateFlag(element.original_language)" alt="flag">
            <!-- recensioni -->
            <div class="vote d-flex">

                <div><strong> Voto: </strong></div>
                <div class="ms-1" v-for="star in voteChanger()"> &#9733; </div>
                <div class="ms-1" v-for="star in (5 - voteChanger())"> &#9734; </div>

            </div>
            <!-- overview -->
            <div><strong>Trama:</strong> {{ element.overview }} </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>
em {
    color: orange;
}


.card {
    min-height: 100%;
    margin-left: 2px;
    // float: left;
    // min-height: 512px;
    min-width: 342px;
    background-color: black;
    // background-image: url(element.poster_path);
    // border: 1px solid white;

    &:hover>.overlay {
        display: block;
        transition: 3s;
    }

    .card:hover>h2 {
        display: none;
    }

    &:first-of-type {
        margin-left: 25px;
    }

    img {
        object-fit: cover;
        height: 100%;
    }

    .overlay {

        height: 100%;
        width: 100%;
        position: absolute;
        background-color: rgb(0, 0, 0);
        border: 1px solid white;
        overflow-y: auto;
        display: none;

        strong {
            color: red;
        }


        .flag {
            width: 20px;
            height: 20px;
            object-fit: contain;
        }

        .vote {
            color: gold;
        }
    }

}
</style>
