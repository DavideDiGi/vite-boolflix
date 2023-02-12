<script>
import axios from 'axios';
import { store } from '../../store';
import AppSearchBar from './AppSearchBar.vue';

export default {
    name: "AppHeader",
    data() {
        return {
            store
        };
    },
    components: {
        AppSearchBar,
    },
    methods: {
        SearchEvent() {
            this.SearchSource('movie');
            this.SearchSource('tv');
        },
        SearchSource(type) {
            let url = 'https://api.themoviedb.org/3/search/';
            console.log('inputText:', store.inputText)

            axios.get(url + type, {
                params: {
                    api_key: 'e05a29e70998f37483213e63a793a9c5',
                    query: store.inputText,
                    language: 'it-IT'
                }
            })
                .then((response) => {
                    console.log(response.data.results);

                    if (type == 'movie') {
                        store.movies = response.data.results;
                    }
                    else {
                        store.series = response.data.results;
                    }
                });
        }
    }
}

</script>

<template>

    <header class="w-100 bg-info h-25">
        <div>
            <AppSearchBar @textContent="SearchEvent" />
        </div>
    </header>

</template>

<style lang="scss" scoped>

</style>
