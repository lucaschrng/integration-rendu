<script setup>
const { toggleNav } = defineProps(['toggleNav'])
</script>

<template>
  <nav>
    <button @click="toggleNav"><ion-icon name="close-outline"></ion-icon></button>
    <a href="/" class="home-button">
      <img src="/img/logo.svg" alt="logo">
      <h1>inance</h1>
    </a>
    <div>
      <a href="/dashboard" class="dashboard-button">
        <img src="/img/dashboard-button-icon.svg" alt="dashboard logo">
        Dashboard
      </a>
      <ul>
        <li>
          <a href="/dashboard">
            <img src="/img/dashboard-icon.svg" alt="dashboard icon">
            Invoices
          </a>
        </li>
        <li>
          <a href="/clients">
            <img src="/img/clients-icon.svg" alt="clients icon">
            Clients
          </a>
        </li>
        <li>
          <a href="/products">
            <img src="/img/products-icon.svg" alt="products icon">
            Products
          </a>
        </li>
        <li>
          <a href="/messages">
            <img src="/img/messages-icon.svg" alt="messages icon">
            Messages
          </a>
        </li>
        <li>
          <a href="/settings">
            <img src="/img/settings-icon.svg" alt="settings icon">
            Settings
          </a>
        </li>
        <li>
          <a href="/help">
            <img src="/img/help-icon.svg" alt="help icon">
            Help
          </a>
        </li>
      </ul>
    </div>
    <a href="/logout" class="logout-button">
      <img src="/img/logout-icon.svg" alt="logout icon">
      Logout
    </a>
  </nav>
</template>

<script>
export default {
  name: "Nav"
}
</script>

<style scoped lang="scss">
nav {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 3rem 4rem;
  
  @media screen and (max-width: 1200px) {
    position: absolute;
    background: #000000;
    z-index: 10;
  }

  > button {
    font-size: 2rem;
    display: none;
    background: rgba(255, 255, 255, 0.2);
    border: none;
    color: #ffffff;
    border-radius: 5px;
    position: absolute;
    top: 1rem;
    right: 1rem;

    @media screen and (max-width: 1200px) {
      display: flex;
    }
  }

  a {
    text-decoration: none;
    color: #ffffff;
  }

  .home-button {
    display: flex;
    align-items: baseline;
    gap: 0.25rem;

    h1 {
      font-size: 38px;
    }
  }

  .dashboard-button {
    color: #000000;
    font-size: 1.5rem;
    width: min-content;
    display: flex;
    align-items: center;
    gap: 1rem;
    background-image: url("/img/gradient-bg.png");
    background-position: center;
    background-size: cover;
    padding: 10px;
    border-radius: 1rem;
  }

  ul {
    padding: 2.75rem 1.25rem;
    display: flex;
    flex-direction: column;
    gap: 1.75rem;
    list-style: none;

    li a {
      display: flex;
      align-items: center;
      gap: 10px;
      color: rgba(255, 255, 255, 0.8);
      font-size: 1.5rem;
      opacity: 0.8;

      img {
        width: 38px;
      }
    }
  }

  .logout-button {
    color: rgba(255, 255, 255, 0.8);
    font-size: 1.5rem;
    display: flex;
    align-items: center;
    gap: 1rem;
    opacity: 0.8;
  }
}
</style>