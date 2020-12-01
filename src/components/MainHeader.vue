<template>
  <header class="main-header">
    <h1 class="main-header_title">
      {{title}}
    </h1>
  </header>
</template>

<script>
export default {
  name: 'MainHeader',
  props: {
    title: String
  }
}
</script>

<style lang="scss">
  .main-header {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    background: white;
    border-radius: 0.5rem;
    box-shadow: 0 0 0.3rem rgba(0,0,0,0.4);
    font-size: 1.6rem;
    margin-bottom: 2rem;
    background: #ef540e;
    color: white;
    font-family: Montserrat, sans-serif;
    text-transform: uppercase;
  }
</style>