<template>
  <footer class="main-footer">
    <div class="main-footer__nav">
      <a href="#"
      :class="{ 'nav__item--disabled' : this.nextAvailable}"
      class=" nav__item item__prev"
      @click.prevent="prev()"
      >
        <img class="prev__icon" src="@/assets/icons/left.svg" alt="">
        <span class="prev__text">Anterior</span>
      </a>
      <a href="#"
      :class="{ 'nav__item--disabled' : !this.nextAvailable}"
      class="nav__item item__next"
      @click.prevent="next()">
        <span class="next__text">Siguiente</span>
        <img class="next__icon" src="@/assets/icons/right.svg" alt="">
      </a>
    </div>
  </footer>
</template>
<script>
export default {
  name: 'PaginationFooter',
  data() {
    return{
      actualPage: 1,
      totalPages: 2,
      nextAvailable: true
    }
  },
  methods: {
    emitPage(e){
      this.$emit("emitPage",  e);
    },
    prev(){
      if (this.actualPage > 1) {
        this.actualPage -= 1;
        this.emitPage(this.actualPage);
        this.nextAvailable = true;
      }
    },
    next(){
      if (this.actualPage < this.totalPages) {
        this.actualPage += 1;
        this.emitPage(this.actualPage);
        this.nextAvailable = false;
      }
    }
  }
}
</script>

<style lang="scss">
  .main-footer{
    box-sizing: border-box;
    background: white;
    border-radius: 0.5rem;
    box-shadow: 0 0 0.3rem rgba(0,0,0,0.4);
    margin-top: 2rem;
    background-color: black;
  }
  .main-footer__nav {
    display: flex;
    font-size: 1.6rem;
    justify-content: space-between;
  }
  .nav__item {
    text-decoration: none;
    color: black;
    background-color: #fc0;
    padding: 1rem 2rem;
    display: flex;
  }
  .nav__prev {
    display: flex;
  }
  .nav__next {
  }
  .prev__icon {
    width: 1.6rem;
    position: relative;
    top: 1px;
  }
  .next__icon{
    width: 1.6rem;
    position: relative;
    top: 2px;
  }
  .nav__item--disabled {
    * {
      opacity: 0.3;
    }
  }
</style>