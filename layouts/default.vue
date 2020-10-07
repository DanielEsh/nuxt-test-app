<template>
  <div class="container">
    <Header/>
    <Nuxt />
  </div>
</template>

<script>
  import Header from '@/components/Header'
  
  export default {
    components: {
      Header
    }
  }
</script>

<style>
  body {
    margin: 0;
    padding: 0;
    font-size: 16px;
    line-height: 24px;
    font-family: "Codec Pro", sans-serif;
    font-weight: 400;
  }
  
  .container {
    max-width: 1920px;
    margin: 0 45px;
    padding-left: 20px;
    padding-right: 20px;
  }
  
  @media (max-width: 400px) {
    .container {
      max-width: 375px;
      padding-left: 16px;
      padding-right: 16px;
    }
  }
</style>
