<template>
  <div>
    <a :class="$style.right" href="#" @click.prevent="showModal()">
      <span :class="$style.rightText">Add new</span>
      <button :class="$style.buttonAdd">+</button>
    </a>
  </div>
</template>

<script>
  export default {
    name: 'ShowModalBtn',
    methods: {
      showModal () {
        this.$store.commit("vehicles/toggleModal");
      },
    }
  }
</script>

<style module>
  .right {
    display: flex;
    align-items: center;
    user-select: none;
  }
  
  .rightText {
    font-weight: 700;
    font-size: 20px;
    line-height: 28px;
    color: var(--primary-color);
    transition: .2s ease;
  }
  
  .right:hover .rightText {
    color: var(--primary-hover);
  }
  
  .right:active .rightText {
    color: var(--primary-active);
  }
  .buttonAdd {
    width: 48px;
    height: 48px;
    margin-left: 20px;
    background: var(--primary-color);
    border: none;
    border-radius: 16px;
    font-size: 22px;
    color: var(--white);
    cursor: pointer;
    transition: .2s ease;
    outline: none;
  }

  .right:hover .buttonAdd {
    background: var(--primary-hover);
  }

  .right:active .buttonAdd {
    background: var(--primary-active);
  }
</style>
