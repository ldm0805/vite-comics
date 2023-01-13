<script>
// Importiamo la componente
import AppHeader from './components/AppHeader.vue'
// import AppContent from './components/AppContent.vue'
import ComicsList from './components/ComicsList.vue'
import AppFooter from './components/AppFooter.vue';

//Utilizza questa componente
export default {

  components: {
    AppHeader,
    // AppContent,
    ComicsList,
    AppFooter,
  }
}
</script>
<!-- Devi utilizzare questa componente-->
<template>
  <div>
    <AppHeader />
    <ComicsList />
    <!-- <AppContent :menu="menu" /> -->
    <AppFooter />
  </div>
</template>

<style lang="scss">
@use './styles/generals.scss' as *;
</style>
