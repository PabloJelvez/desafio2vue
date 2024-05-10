<template>
  <div id="app">
    
<h1>Crea tu tarjeta de credito</h1>
<CreditsCard />
    
  </div>
</template>

<script>
import CreditsCard from './components/CreditsCard.vue'
export default {
  name: 'App',
  components: {
    CreditsCard
    
  }
}
</script>

<style>
body{
  background: linear-gradient(rgb(196, 198, 70), rgb(218, 113, 113));
}
h1{
  text-align: center;
}
</style>
