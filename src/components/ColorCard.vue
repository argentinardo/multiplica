<template>
  <div class="color-card">
    <span class="color-card__id">{{colorId}}</span>
    <span class="color-card__name">{{colorName}}</span>
    <span class="color-card__hex">{{colorHex}}</span>
    <span class="color-card__pantone">{{colorPantone}}</span>
  </div>
</template>

<script>
export default {
  name: 'ColorContainer',
  props: {
    colorId: String,
    colorName: String,
    colorHex: String,
    colorPantone: String
  }
}
</script>

<style lang="scss">
</style>