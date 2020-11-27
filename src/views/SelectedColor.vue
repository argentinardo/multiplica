<template>
  <article class="home">
    <main-header></main-header>
    <color-container></color-container>
    <pagination-footer></pagination-footer>
  </article>
</template>

<script>
// @ is an alias to /src
import MainHeader from '@/components/MainHeader.vue'
import PaginationFooter from '@/components/PaginationFooter.vue'
import ColorContainer from '../components/ColorContainer.vue'

export default {
  name: 'Home',
  components: {
    MainHeader,
    PaginationFooter,
    ColorContainer
  }
}
</script>