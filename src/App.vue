<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="layout">
    <header>

      <div class="wrapper">

        <nav>
          <RouterLink :to="{name: 'home'}">Home</RouterLink>
          <RouterLink :to="{name: 'about'}">About</RouterLink>
        </nav>
      </div>
    </header>

    <RouterView />
  </div>
</template>

<style scoped>
#layout{
  font-family: Avenir;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
nav{
  padding: 30px;
  display: flex;
  gap: 8px;
  justify-content: center;
}
nav a{
  font-weight: bold;
  color: #2c3e50;
}
nav a.router-link-exact-active{
  color: #42b983;
}
</style>
