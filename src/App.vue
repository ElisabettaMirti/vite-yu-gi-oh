<script>
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';

export default {
  data(){

  },
  components: {
    AppMain,
    AppHeader
  }
}
</script>

<template>

<AppHeader />

<main>
  <AppMain />
</main>


</template>

<style lang="scss" scoped>
  @use './styles/partials/mixins.scss' as *;
  @use './styles/partials/variables.scss' as *;
  @use './styles/general.scss';
</style>
