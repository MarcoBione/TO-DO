<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

import HeaderComponent from '../src/components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
</script>

<template>
  
  <div class="core-app">
    <div class="wrapper">
      <HeaderComponent/>
      <MainComponent/>
    </div>
  </div>
  

  <RouterView />
</template> 


<style scoped>
.core-app{
  background-color: #0b032d;
  width: 100%;
  height: 100vh;
}
.wrapper{
  margin: 0 auto;
  width: 1200px;
  color: white;
}

</style>
