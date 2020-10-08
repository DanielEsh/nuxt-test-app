<template>
  <div class="container">
    <div :class="{ [$style.modalOverlay]: this.$store.state.vehicles.isModalActive }">
      <Header/>
      <Nuxt />
    </div>
    <div class="modal-overlay">
      <add-modal
        class="modal"
        :class="{ modalShow: this.$store.state.vehicles.isModalActive }"
        @close="closeModal"/>
    </div>
  </div>
</template>

<script>
  import Header from '@/components/Header'
  import AddModal from '@/components/add-modal'
  
  export default {
    components: {
      Header,
      AddModal
    },
    methods: {
      closeModal() {
        this.$store.commit("vehicles/toggleModal");
      }
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

  @media (max-width: 760px) {
    .container {
      max-width: 1920px;
      margin: 0 10px;
      padding-left: 20px;
      padding-right: 20px;
    }
  }
  @media (max-width: 400px) {
    .container {
      max-width: 375px;
      padding-left: 16px;
      padding-right: 16px;
    }
  }
</style>

<style module>
  .modalOverlay{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    filter: blur(12px);
    overflow-y: hidden;
  }

</style>
