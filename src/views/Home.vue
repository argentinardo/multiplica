<template>
  <article class="home">
    <main-header title="Colores"></main-header>
    <color-container :currentPage="this.updatePage"></color-container>
    <pagination-footer @emitPage="emitHola"></pagination-footer>
  </article>
</template>

<script>
// @ is an alias to /src
import MainHeader from '@/components/MainHeader.vue'
import PaginationFooter from '@/components/PaginationFooter.vue'
import ColorContainer from '@/components/ColorContainer.vue'

export default {
  name: 'Home',
  components: {
    MainHeader,
    PaginationFooter,
    ColorContainer
  },
  data(){
    return {
    actualPage : 1
    }
  },
  computed: {
    updatePage(){
      return this.actualPage;
    }
  },
  methods :{
    emitHola(e){
      this.actualPage = e;
    }
  }
}
</script>

<style lang="scss">
.home{
  box-sizing:border-box;
  display: flex;
  flex-direction: column;
  font-family: 'Open Sans', sans-serif;
  font-weight: 400;
}
</style>