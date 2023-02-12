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

    }
}



</script>

<template>

    <form action="#">
        <input v-model="store.inputText" type="text" placeholder="Cosa vuoi guardare?">
        <button @click="$emit('TextContent')">Cerca</button>
    </form>

</template>

<style lang="scss" scoped>

</style>
