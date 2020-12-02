<template>
    <div class="color-card" :class="{'color-card--max': maximized}"  :style="{ backgroundColor: this.colorHex }">
  <copy-to-clipboard @copy="maximize"  :text="this.$props.colorHex">
      <span class="color-card__year">{{colorYear}}</span>
      <span v-if="maximized"  class="color-card__copy">¡Copiado!</span>
      <span v-if="!maximized"  class="color-card__name">{{colorName}}</span>
        <span disabled v-if="!maximized" class="color-card__hex">{{colorHex}}</span>
      <span class="color-card__pantone">{{colorPantone}}</span>
  </copy-to-clipboard>
    </div>
</template>

<script>
import CopyToClipboard from 'vue-copy-to-clipboard'
export default {
  components: {CopyToClipboard},
  name: 'ColorContainer',
  props: {
    colorYear: Number,
    colorName: String,
    colorHex: String,
    colorPantone: String
  },
  data(){
    return {
      maximized: false,
      copiedText: "antes"
    }
  },
  methods: {
    maximize() {
      this.maximized = !this.maximized
      console.log("que onda?")
    }
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
    box-shadow: 0 0 0.3rem rgba(0,0,0,0.6);
    color: white;
    text-shadow: 0 0 0.1rem rgba(0,0,0,1);
    font-size: 2rem;
    padding: 1rem;
    flex: 0 32%;
    margin-bottom:2rem;
    transition: all 0.2s ease-out;
    &:hover {
      transition: all 0.1s ease-out;
      box-shadow: 0 0 0.6rem rgba(0,0,0,0.3);
      transform: scale(1.02);
      cursor: pointer;
    }
    &.color-card--max {
      position: absolute;
      width: 100%;
      height: 100%;
      justify-content: space-between;
      &:hover{
        transform: scale(1);
      }
      & > span {
        display: flex;
        flex-direction: column;
        height: 100%;
        justify-content: space-between;
      }
    }
   & > span {
      display: flex;
      flex-direction: column;
      height: 100%;
      justify-content: space-between;
    }
  }
  .color-card__copy {
    font-size: 2.5rem;
  }
  .color-card__year {
    align-self: flex-start;
    font-size: 1.6rem;
  }
  .color-card__name {
    line-height: 4rem;
  }
  .color-card__hex {
    line-height: 4rem;
    font-weight: 600;
    text-shadow: 0 0 0.15rem rgba(0,0,0,2);
    font-size: 2rem;
  }
  .color-card__pantone {
    align-self: flex-end;
    font-size: 1.6rem;
  }
</style>