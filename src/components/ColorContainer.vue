<template>
  <div class="color-container">
    <color-card
     v-for="color in colors.data"
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
    colors: [],
    currentUrl: this.currentPage
   }
  },
  watch: {
    currentPage: function(){
      let sufix = ""
      this.currentPage == 2 ? sufix = "?page=2" : sufix = ""
      this.jsonUrl = "https://reqres.in/api/colors" + sufix
      this.getData()
    }
  },
  props: {
    currentPage: Number
  },
  methods: {
    getData(){
      axios
        .get( this.jsonUrl)
        .then( response => (this.colors = response.data))
        .catch( error => console.log(error))
    }
  },
  mounted(){
    this.getData()
  },
  components: { ColorCard },
  name: 'ColorContainer'
}
</script>

<style lang="scss">
  .color-container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
</style>