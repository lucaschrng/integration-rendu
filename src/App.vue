<script setup>
import Navbar from './components/Navbar.vue';
import Sidebar from "./components/Sidebar.vue";
</script>

<template>
  <header>
    <Navbar/>
  </header>
  <main>
    <div class="main">
      <div class="search-bar">
        <span>Hi, Rogers</span>
        <div>
          <img src="/img/search-icon.svg" alt="search icon">
          <input type="text" name="search" id="search" placeholder="Search">
        </div>
      </div>
    </div>
    <Sidebar/>
  </main>
</template>

<style scoped lang="scss">
main {
  width: 100%;
  display: flex;
}

.main {
  width: 100%;
}

.search-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 48px 0rem;

  > span {
    font-size: 35px;
  }

  > div {
    width: 50%;
    display: flex;
    padding: 0.5rem 1rem;
    background: #ffffff;
    border-radius: 15px;
    gap: 5px;

    input {
      border: none;
      outline: none;
    }
  }
}
</style>