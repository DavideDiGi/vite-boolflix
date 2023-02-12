<script>
// import axios from 'axios';
import { store } from './store'

import AppHeader from './components/Header/AppHeader.vue'
import AppMain from './components/Main/AppMain.vue'

export default {
  name: 'App',
  data() {
    return {
      store,
    }
  },
  components: {

    AppHeader,
    AppMain,

  },
}
</script>

<template>
  <div class="container bg-secondary vh-100 p-0">
    <AppHeader />

    <AppMain />
  </div>

</template>

<style lang="scss">
@import './styles/main.scss';

body {
  background-color: gray;
}
</style>
