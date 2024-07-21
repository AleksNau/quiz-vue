<template>
  <div>
    <button aria-label="Toggle Menu" class="burger-button" v-bind:class="{ open: menuOpen }" @click="handleToggleMenu">
      <span class="burger-bars"></span>
      <span class="burger-bars"></span>
      <span class="burger-bars"></span>
    </button>
    <ul v-if="menuOpen" class="menu-container">
      <span aria-label="Close Menu" class="menu-close" @click="handleCloseMenu">
        <svg width="28" height="28" viewBox="0 0 28 28" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M28 2.82L25.18 0L14 11.18L2.82 0L0 2.82L11.18 14L0 25.18L2.82 28L14 16.82L25.18 28L28 25.18L16.82 14L28 2.82Z" fill="#FFC700"/>
</svg>

      </span>
      <li class="menu-item"><router-link class="menu-item-text" to="/">Главная</router-link></li>
      <li class="menu-item"><router-link class="menu-item-text" to="/result">Информация о тесте</router-link></li>
      <li class="menu-item"><router-link class="menu-item-text" to="/quiz">Пройти тест</router-link></li>
    </ul>


  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
      menuClosed: false
    };
  },
  methods: {
    handleToggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    handleCloseMenu() {
      this.menuClosed = true;
      if (this.menuClosed) {
        this.menuOpen = false;
      }
    }
  }
};
</script>


<style>
.burger-button {
  position: absolute;
  width: 24px;
  height: 16px;
  left: 17px;
  top: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  cursor: pointer;
  padding: 0;
  margin: 0;
  background-color: transparent;
  border: none;
}
.burger-bars {
  height: 2px;
  background-color: #696969;
  width:24px
}

.menu-container {
  list-style-type: none;
  margin: 0;
  position: relative;
  width: 100%;
  padding: 110px 10px 10px 23px;
  background-color: #181818;
  min-height: 100vh;
  z-index: 999;
}

.menu-close {
  width: 28px;
  height: 28px;
  background-color: transparent;
  position: absolute;
  top: 18px;
  right: 13px;
}

.menu-item {
  font-family: Roboto;
  font-size: 16px;
  line-height: 22px;
  text-align: left;

}

.menu-item-text {
  text-decoration: none;
  text-transform: uppercase;
  color: #FFFFFF;
}

.menu-item-text:active {
  color: #F4CE0C;
}




</style>