<script setup>
const { imgUrl, name, number, currency, background, color } = defineProps(['imgUrl', 'name', 'number', 'currency', 'background', 'color']);
</script>

<template>
  <div class="asset-card" :style="`background: ${background}; color: ${color};`">
    <img :src="imgUrl" alt="logo">
    <span>{{ name }}</span>
    <div class="infos">
      <span>{{ number }}</span>
      <span>{{ currency }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "AssetCard"
}
</script>

<style scoped lang="scss">
.asset-card {
  display: flex;
  flex-direction: column;
  align-items: baseline;
  font-weight: 600;
  font-size: 19px;
  padding: 13px;
  border-radius: 30px;

  img {
    height: 85px;
  }

  .infos {
    width: 100%;
    display: flex;
    justify-content: space-between;
    font-size: 27px;
    margin-top: 3px;
  }
}
</style>