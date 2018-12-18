<template>
  <div id="app">
    <app-header />
    <transition name="fade" mode="out-in">
      <router-view class="inhoud" />
    </transition>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    AppHeader
  }
}
</script>



<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font: 62.5% 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
  font-size: 1.6rem;
}

a {
  text-decoration: none;
  color: inherit;
}

.inhoud {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    padding: 4rem;
    padding-top: 8rem;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.2s ease;
}
</style>
