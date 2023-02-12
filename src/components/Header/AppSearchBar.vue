<script>
import { store } from '../../store';

export default {
    name: 'AppSearchBar',
    data() {
        return {
            store
        }
    },
    methods: {
        // updateSelect(element) {
        // axios
        //     .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${element}`)
        //     .then((response) => {
        //         this.store.archetypeChosen = response.data.data;
        //         console.log('archetype scelta array', response.data.data);
        //     });

    }
}
        // findMovie() {

        // }


</script>

<template>

    <form action="#">
        <input v-model="store.inputText" type="text">
        <button @click="$emit('TextContent')">Cerca</button>
    </form>

</template>

<style lang="scss" scoped>

</style>
