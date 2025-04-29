<template>
  <div>
    <nav>
      <header>
        <div class="container-icon">
          <img src="../public/img/iconCard.png" alt="Logo" class="icon" />
        </div>
        <div class="container-menu">
          <router-link to="/" class="menu" id="cards">Home</router-link>
          <router-link to="/about" class="menu" id="regras">About</router-link>
        </div>
      </header>
    </nav>
    <router-view />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  background-color: #2c3e50;
  width: 100%;
  text-align: center;
  font-family: "Passero One", sans-serif;
}

header {
  display: flex;
  padding: 5px;
  height: 70px;
}

.container-menu {
  flex-grow: 1;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 10px;
}

.menu {
  color: #fff;
  text-decoration: none;
  font-size: 30px;
  margin: 0 10px;
  transition: all 0.3s ease;
  font-family: "Passero One", sans-serif;
}

.menu:hover {
  color: #ffcc00;
}

.container-icon {
  flex-grow: 2;
  flex-basis: 50px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 10px;
}

.icon {
  width: 50px;
  cursor: pointer;
  transition: all 0.5s ease;
}

.icon:hover {
  transform: rotate(180deg);
}
</style>
