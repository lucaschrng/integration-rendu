<script setup>
import {onMounted, ref} from "vue";
import Navbar from './components/Navbar.vue';
import Sidebar from "./components/Sidebar.vue";

let showNav = ref(true);
const toggleNav = () => showNav.value = !showNav.value;

onMounted(() => {
  if (window.innerWidth <= 1200) showNav.value = false
  else showNav.value = true
  window.addEventListener('resize', () => {
    if (window.innerWidth <= 1200) showNav.value = false
    else showNav.value = true
  })
})
</script>

<template>
  <header>
    <Navbar v-if="showNav" :toggleNav="toggleNav"/>
  </header>
  <main>
    <div class="main">
      <div class="search-bar">
        <button @click="toggleNav"><ion-icon name="menu-outline"></ion-icon></button>
        <span>Hi, Rogers</span>
        <div class="search-input">
          <img src="/img/search-icon.svg" alt="search icon">
          <input type="text" name="search" id="search" placeholder="Search">
        </div>
        <div class="info-bar">
          <img src="/img/notification-icon.svg" alt="notification icon">
          <img src="/img/profile-icon.png" alt="profile icon">
        </div>
      </div>
      <div class="main-content">
        <div class="controls">
          <div class="left-controls">
            <span class="balance">Total Balance</span>
            <span class="balance-number">0.97894652<span class="tag">BTC</span></span>
            <span class="amount">$40,123.56</span>
          </div>
          <ul class="right-controls">
            <li class="active">
              <button>Portfolio</button>
            </li>
            <li>
              <button>Funding</button>
            </li>
            <li>
              <button>Assets</button>
            </li>
            <li>
              <button>P2P</button>
            </li>
          </ul>
        </div>
        <div class="diagram">

          <div class="controls">

            <div class="left">
              <span>1H</span>
              <span>1D</span>
              <span>3D</span>
              <span>1W</span>
              <span>1M</span>
              <span>1H</span>
            </div>

            <div class="right">
              <div>
                <img class="currency" src="/img/bitcoin-exchange-logo.png" alt="">
                <span>BTC</span>
                <img src="/img/down-arrow.svg" alt="">
              </div>
              <img src="/img/exchange-arrows.svg" alt="">
              <div>
                <img class="currency" src="/img/eth-exchange-logo.png" alt="">
                <span>BTC</span>
                <img src="/img/down-arrow.svg" alt="">
              </div>
            </div>

          </div>

          <ul class="dollars">
            <li>$700</li>
            <li>$600</li>
            <li>$500</li>
            <li>$400</li>
            <li>$300</li>
            <li>$200</li>
            <li>$100</li>
          </ul>

          <ul class="date">
            <li>5NOV</li>
            <li>6NOV</li>
            <li>7NOV</li>
            <li>8NOV</li>
            <li>9NOV</li>
            <li>10NOV</li>
            <li>11OV</li>
            <li>12NOV</li>
            <li>13NOV</li>
            <li>14NOV</li>
            <li>15NOV</li>
            <li>16NOV</li>
          </ul>

          <img class="curve" src="/img/curves.png" alt="">

        </div>
        <div class="transaction-title">
          <h2>Recent transactions</h2>
          <a href="/all-coins">See all coins</a>
        </div>
        <ul>
          <li class="transaction-recent">
            <img src="/img/bitcoin-logo-3.svg" alt="">
            <div>
              <span>Bitcoin</span>
              <span class="currency">BTC</span>
            </div>
            <div>
              <span>Market Cap</span>
              <span class="price">$40,243.70</span>
            </div>
            <div>
              <span>24h change</span>
              <span class="change">+1,56</span>
            </div>
            <img src="/img/worm1.svg" alt="">
            <button>Trade</button>
          </li>
          <li class="transaction-recent">
            <img src="/img/etherum-logo-3.svg" alt="">
            <div>
              <span>Etherum</span>
              <span class="currency">ETH</span>
            </div>
            <div>
              <span>Market Cap</span>
              <span class="price">$30,721.73</span>
            </div>
            <div>
              <span>24h change</span>
              <span class="change negative">-1,41</span>
            </div>
            <img src="/img/worm2.svg" alt="">
            <button>Trade</button>
          </li>
        </ul>
      </div>
    </div>
    <Sidebar/>
  </main>
</template>

<style scoped lang="scss">
main {
  width: 100%;
  max-height: 100vh;
  display: flex;

  @media screen and (max-width: 1700px) {
    display: block;
    padding: 0 2rem 0rem 0rem;
    overflow-y: scroll;
    -ms-overflow-style: none;
    scrollbar-width: none;

    &::-webkit-scrollbar {
      display: none;
    }
  }

  @media screen and (max-width: 1200px) {
    padding: 0 2rem;
  }
}

.main {
  width: 100%;
  max-height: 100vh;
  overflow-y: scroll;
  -ms-overflow-style: none;
  scrollbar-width: none;

  &::-webkit-scrollbar {
    display: none;
  }

  @media screen and (max-width: 1700px) {
    max-height: min-content;
  }
}

.search-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 48px 0rem;

  @media screen and (max-width: 900px) {
    display: grid;
    grid-template-columns: min-content, repeat(2, 1fr);
    gap: 1rem;
  }

  > span {
    font-size: 35px;
  }

  > button {
    font-size: 3rem;
    display: none;
    background: transparent;
    border: none;
    color: #ffffff;
    border-radius: 5px;

    @media screen and (max-width: 1200px) {
      display: flex;
    }
  }

  > .search-input {
    width: 50%;
    display: flex;
    padding: 0.5rem 1rem;
    background: #ffffff;
    border-radius: 15px;
    gap: 5px;

    @media screen and (max-width: 900px) {
      grid-row: 2;
      grid-column: 1/4;
      width: 100%;
    }

    input {
      border: none;
      outline: none;
    }
  }

  > .info-bar {
    display: none;
    gap: 2rem;

    @media screen and (max-width: 1700px) {
      display: flex;
    }

    @media screen and (max-width: 900px) {
      justify-content: end;
    }
  }
}

.controls {
  display: flex;
  justify-content: space-between;
  align-items: center;

  @media screen and (max-width: 900px) {
    flex-direction: column;
    align-items: start;
    gap: 1rem;
  }
}

.left-controls {
  display: flex;
  flex-direction: column;
  gap: 10px;
  font-size: 22px;

  .balance {
    font-weight: 800;
    opacity: 0.8;
  }

  .balance-number {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 29px;
    font-weight: 700;

    .tag {
      font-size: 15px;
      color: black;
      background: #FAFF00;
      padding: 3px 9px;
      border-radius: 8px;
    }
  }

  .amount {
    font-weight: 600;
    opacity: 0.7;
  }
}

.right-controls {
  display: flex;
  align-items: center;
  gap: 24px;
  list-style: none;
  background: #292727;
  padding: 11px 19px;
  border-radius: 1rem;

  @media screen and (max-width: 900px) {
    width: 100%;
    justify-content: space-between;
  }

  button {
    background: transparent;
    border: none;
    outline: none;
    color: white;
    font-family: 'Poppins', sans-serif;
    font-size: 22px;
    cursor: pointer;
    padding: 6px 22px;
  }

  .active button {
    background: #0D0C0C;
    border-radius: 1rem;
  }
}

.diagram {
  margin-top: 2rem;
  background: rgba(48, 53, 65, 0.67);
  border-radius: 30px;
  display: grid;
  grid-template-areas:
      'controls controls'
      'dollars   curves '
      '   .       date  ';
  grid-template-columns: min-content 1fr;
  grid-template-rows: min-content 1fr min-content;
  padding: 2rem;

  .controls {
    grid-area: controls;
    display: flex;
    justify-content: space-between;

    .left {
      display: flex;
      gap: 0.5rem;

      span {
        font-weight: 600;
        font-size: 27px;
        background: #000000;
        padding: 0 4px;
        border-radius: 5px;
      }
    }

    .right {
      display: flex;
      align-items: center;
      gap: 1rem;

      div {
        display: flex;
        align-items: center;
        gap: 1rem;
        background: #000000;
        padding: 6px 1rem;

        span {
          opacity: 0.7;
          font-size: 17px;
          font-weight: 600;
        }

        .currency {
          height: 30px;
        }
      }
    }
  }

  .dollars {
    list-style: none;
    font-weight: 600;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    opacity: 0.7;
    grid-area: dollars;
  }

  .date {
    list-style: none;
    font-weight: 600;
    display: flex;
    justify-content: space-evenly;
    opacity: 0.7;
    grid-area: date;
  }

  .curve {
    grid-area: curves;
    align-self: center;
    justify-self: center;
    height: 90%;
    padding: 2rem 0;

    @media screen and (max-width: 900px) {
      height: 80%;
    }
  }
}

.transaction-title {
  display: flex;
  justify-content: space-between;
  padding: 1rem 2rem;

  a {
    color: #ffffff;
    opacity: 0.7;
    text-decoration: none;
    font-size: 1.5rem;
    font-weight: 600;
  }
}

.transaction-recent {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(32, 25, 43, 0.7);
  padding: 1rem;
  border-radius: 30px;
  margin: 1rem 2rem;
  box-shadow: inset 0 0 5px 5px rgba(0, 0, 0, 1);

  > div {
    display: flex;
    flex-direction: column;

    .currency {
      opacity: 0.7;
    }

    .price {
      font-weight: 600;
      color: #1970D6;
      opacity: 0.7;
    }

    .change {
      font-weight: 600;
      color: #4AD619;
      opacity: 0.7;

      &.negative {
        color: #D61919;
      }
    }
  }

  button {
    color: #ffffff;
    background: #000000;
    border: none;
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 17px;
    height: min-content;
    padding: 6px 13px;
    border-radius: 1000px;
  }
}

</style>