<template>
  <div :class="{ [$style.dark]: this.$store.state.vehicles.isNightMode }">
    <div @click.prevent="viewCardDetails" :class="$style.listItemLink">
      <img :src='`${vehicle.preview}`' alt="" :class="$style.itemImg">
      <div :class="$style.itemContent">
        <h3 :class="$style.itemTitle">{{vehicle.name}}</h3>
        <p :class="$style.itemDescription">{{vehicle.description}}</p>
        <span :class="$style.itemRent">{{vehicle.rent}} $/h</span>
      </div>
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
        item: this.vehicle
      }
    },
    methods: {
      viewCardDetails(){
        this.$router.push('/' + this.item.name)
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
    cursor: pointer;
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
  .dark .listItemLink {
    background-color: var(--night);
  }
  .dark .itemTitle {
    color: var(--white);
  }
  .dark .itemDescription {
    color: var(--night-text);
  }
  @media (max-width: 1700px) {
    .listItem {
      width: 30%;
    }
  }

  @media (max-width: 1150px) {
    .listItem {
      width: 46%;
    }
  }
  @media (max-width: 950px) {
    .listItem {
      width: 100%;
    }
  }
  @media (max-width: 700px) {
    .listItemLink {
      margin-bottom: 20px;
    }
  }
  @media (max-width: 520px) {
    .listItem {
      padding: 0;
    }
    .listItemLink {
      padding: 20px;
    }
  
    .itemImg {
      margin-right: 20px;
    }
  
    .itemTitle {
      font-size: 16px;
    }
  }
</style>
