<template>
  <footer class="main-footer">
    <div class="main-footer__nav">
      <a href="#" class="nav__item item__prev nav__item--disabled" @click.prevent="prev()">
        &lt; Anterior
      </a>
      <a href="#" class="nav__item item__next"  @click.prevent="next()">
        Siguiente &gt;
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
      totalPages: 2
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
      }
    },
    next(){
      if (this.actualPage < this.totalPage) {
        this.actualPage += 1;
        this.emitPage(this.actualPage);
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
  }
  .main-footer__nav {
    display: flex;
    font-size: 1.6rem;
    justify-content: space-between;
    padding:1rem 2rem 1rem 2rem;
  }
  .nav__item {
    text-decoration: none;
    color: black;
  }
  .nav__item--disabled {
    color: rgb(160, 160, 160);
  }
  .nav__prev {
    display: flex;
  }
  .nav__next {
    display: flex;
  }
</style>