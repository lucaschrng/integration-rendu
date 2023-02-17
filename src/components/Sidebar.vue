<script setup>
import TransactionCard from "./TransactionCard.vue";
import AssetCard from "./AssetCard.vue";
</script>

<template>
  <div class="sidebar">
    <div class="info-bar">
      <img src="/img/notification-icon.svg" alt="notification icon">
      <img src="/img/profile-icon.png" alt="profile icon">
    </div>
    <div class="recent-transactions">
      <h2>Recent Transactions</h2>
      <TransactionCard
          iconUrl="/img/usdt-logo.png"
          name="Usdt"
          type="Received"
          price="+ $3,546"
          date="Today, 13:45 pm"
      />
      <TransactionCard
          iconUrl="/img/binance-logo.png"
          name="BNB"
          type="Buy"
          price="+ 0.7546"
          date="Today, 5:45 am"
      />
      <TransactionCard
          iconUrl="/img/lite-logo.png"
          name="Lite Coin"
          type="Withdrawal"
          price="- 0.7546"
          date="Today 7:55 am"
      />
      <TransactionCard
          iconUrl="/img/bitcoin-logo.png"
          name="Bitcoin"
          type="Received"
          price="+ 2.7546"
          date="Today 8:55 am"
      />
      <TransactionCard
          iconUrl="/img/etherum-logo.png"
          name="Etherum"
          type="Received"
          price="+ 1.646"
          date="Today 10:02 am"
      />
    </div>
    <div>
      <h2>Assets</h2>
      <div class="assets">
        <AssetCard
            imgUrl="/img/bitcoin-logo-2.svg"
            name="Bitcoin"
            number="121,6450.45"
            currency="BTC"
            background="linear-gradient(98.73deg, #611D8D 35.75%, #2F7EC1 73.26%)"
            color="#ffffff"
        />
        <AssetCard
            imgUrl="/img/etherum-logo-2.png"
            name="Etherum"
            number="143,850.45"
            currency="ETH"
            background="linear-gradient(99.56deg, #FAFF00 35.82%, #29ABE2 64.75%, rgba(255, 255, 255, 0.7) 91.33%)"
            color="#000000"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sidebar",
}
</script>

<style scoped lang="scss">
.sidebar {
  height: 100vh;
  min-width: 446px;
  padding: 3rem 34px;
  overflow-y: scroll;
  -ms-overflow-style: none;
  scrollbar-width: none;

  &::-webkit-scrollbar {
    display: none;
  }

  @media screen and (max-width: 1700px) {
    max-height: min-content;
    height: min-content;
  }

  > div > h2 {
    font-size: 22px;
    padding: 1rem 0;
  }

  .info-bar {
    display: flex;
    justify-content: space-between;
    margin-bottom: 5rem;

    @media screen and (max-width: 1700px) {
      display: none;
    }
  }

  .assets {
    display: flex;
    flex-direction: column;
    gap: 28px;
  }
}
</style>