<template>
  <div @click.prevent="test" :class="$style.listItemLink">
      <img :src='`${vehicle.preview}`' alt="" :class="$style.itemImg">
      <div :class="$style.itemContent">
        <h3 :class="$style.itemTitle">{{vehicle.name}}</h3>
        <p :class="$style.itemDescription">{{vehicle.description}}</p>
        <span :class="$style.itemRent">{{vehicle.rent}} $/h</span>
      </div>
  </div>
</template>

<script>
  export default {
    name: 'Card',
    props: {
      vehicle: Object
    },
    data(){
      return {
        a: this.vehicle
      }
    },
    methods: {
      test(){
        this.$router.push('/' + this.a.name)
      }
    }
  }
</script>

<style module>
  .listItem {
    width: 31% !important;
    padding: 0 25px;
    user-select: none;
  }
  .listItemLink {
    display: flex;
    margin-bottom: 32px;
    padding: 25px 32px;
    background: var(--white);
    border-radius: 32px;
  }
  .itemImg {
    width: 88px;
    height: 88px;
    margin-right: 24px;
    border-radius: 24px;
  }
  .itemContent {
    display: flex;
    flex-direction: column;
  }
  .itemTitle {
    margin: 0 0 12px 0;
    font-weight: 700;
    line-height: 18px;
    color: var(--night);
  }
  .itemDescription {
    margin: 0 0 16px 0;
    font-weight: 300;
    font-size: 12px;
    line-height: 18px;
    color: var(--light-text);
  }
  .itemRent {
    margin: 0;
    font-weight: 700;
    font-size: 14px;
    line-height: 21px;
    color: var(--secondary);
  }
</style>
