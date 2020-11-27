<template>
  <color-card></color-card>
</template>

<script>
import ColorCard from './ColorCard.vue'
export default {
  components: { ColorCard },
  name: 'ColorContainer',
  props: {
    title: String
  }
}
</script>

<style lang="scss">

</style>