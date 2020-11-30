<template>
  <div class="color-container">
    <color-card
     v-for="color in colors.data.data"
     :key="color.id"
     :colorYear="color.year"
     :colorId="color.id"
     :colorName="color.name"
     :colorHex="color.color"
     :colorPantone="color.pantone_value"
     >
    </color-card>
  </div>
</template>

<script>
import ColorCard from './ColorCard.vue'
  import axios from 'axios'
export default {
  data() {
   return {
    jsonUrl: "https://reqres.in/api/colors",
    colors: []
   }
  },
  mounted(){
    axios
      .get( this.jsonUrl)
      .then( response => (this.colors = response))
      .catch( error => console.log(error))
  },
  components: { ColorCard },
  name: 'ColorContainer',
  props: {
    title: String
  }
}
</script>

<style lang="scss">
  .color-container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
</style>