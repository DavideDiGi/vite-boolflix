<script>
import { store } from './store'
import AppHeader from './components/Header/AppHeader.vue'
import AppSearchBar from './components/Header/AppSearchBar.vue'
import AppInput from './components/Header/AppInput.vue'
import AppButton from './components/Header/AppButton.vue'
import AppMain from './components/Main/AppMain.vue'
import AppCardContainer from './components/Main/AppCardContainer.vue'
import AppCardMovies from './components/Main/AppCardMovies.vue'
import AppCardSeries from './components/Main/AppCardSeries.vue'

export default {
  name: 'App',
  data() {
    return {
      store
    }
  },
  components: {
    AppHeader,
    AppSearchBar,
    AppInput,
    AppButton,
    AppMain,
    AppCardContainer,
    AppCardMovies,
    AppCardSeries
  }
}
</script>

<template>

  <AppHeader />
  <AppSearchBar />
  <AppInput />
  <AppButton />

  <AppMain />
  <AppCardContainer />
  <AppCardMovies />
  <AppCardSeries />

</template>

<style lang="scss">
@import './styles/main.scss';
</style>
