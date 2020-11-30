<template>
  <footer class="main-footer">
    <div class="main-footer__nav">
      <a href="#" class="nav__item item__prev nav__item--disabled">
        &lt; Anterior
      </a>
      <a href="#" class="nav__item item__next">
        Siguiente &gt;
      </a>
    </div>
  </footer>
</template>
<script>
export default {
  name: 'PaginationFooter',
  props: {
    title: String
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