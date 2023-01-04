<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="sticky-top">
  

 
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/xulytruyen">xulytruyen</RouterLink>
  </div>
  <body
  class="
    antialiased
    bg-gradient-to-r
    from-pink-300
    via-purple-300
    to-indigo-400
  "
>
<RouterView />
</body>
  
</template>

