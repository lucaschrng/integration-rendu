<script setup>
const { iconUrl, name, type, price, date } = defineProps(['iconUrl', 'name', 'type', 'price', 'date']);
</script>

<template>
  <div class="transaction-card">
    <img :src="iconUrl" alt="company logo">
    <div>
      <span>{{ name }}</span>
      <span class="sub-info">{{ type }}</span>
    </div>
    <div>
      <span :class="`price ${ price[0] === '-' ? 'negative':'' }`">{{ price }}</span>
      <span class="sub-info">{{ date }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TransactionCard"
}
</script>

<style scoped lang="scss">
.transaction-card {
  display: flex;
  gap: 1rem;
  align-items: center;
  padding: 1rem 0.5rem;
  font-size: 19px;
  font-weight: 600;

  @media screen and (max-width: 550px) {
    display: grid;
    grid-template-columns: repeat(2, min-content);
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 20px;
    padding: 1rem;
    margin-bottom: 1rem;
  }

  img {
    height: 52px;

    @media screen and (max-width: 550px) {
      grid-column: 1/3;
    }
  }

  > div {
    display: flex;
    flex-direction: column;

    &:nth-child(2) {
      width: 100%;

      @media screen and (max-width: 550px) {
        width: min-content;
      }
    }

    span {
      white-space: nowrap;
    }

    .sub-info {
      opacity: 0.7;
    }

    .price {
      color: #4AD619;

      &.negative {
        color: #D61919;
      }
    }
  }
}
</style>