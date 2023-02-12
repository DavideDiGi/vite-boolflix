<script>
// import axios from 'axios';
import { store } from './store'

import AppHeader from './components/Header/AppHeader.vue'
import AppInput from './components/Header/AppInput.vue'
import AppButton from './components/Header/AppButton.vue'
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
    AppInput,
    AppButton,
    AppMain,

  },
}
</script>

<template>
  <div class="container bg-dark vh-100 p-0">
    <AppHeader />
    <AppInput />
    <AppButton />

    <AppMain />
  </div>

</template>

<style lang="scss">
@import './styles/main.scss';

body {
  background-color: gray;
}
</style>
