<template>
  <div class="color-card" :style="{ backgroundColor: this.colorHex }">
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
  .color-card {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    background: white;
    border-radius: 0.5rem;
    min-width: 8rem;
    width: calc(100%/3);
    box-shadow: 0 0 0.3rem rgba(0,0,0,0.4);
    color: white;
    text-shadow: 0 0 0.1rem rgba(0,0,0,1);
    font-size: 2rem;
    padding: 1rem;
  }
  .color-card__id {
    align-self: flex-start;
  }
  .color-card__name {
    line-height: 4rem;
  }
  .color-card__hex {
    line-height: 4rem;
    font-weight: 600;
    text-shadow: 0 0 0.15rem rgba(0,0,0,2);
  }
  .color-card__pantone {
    align-self: flex-end;
  }
</style>