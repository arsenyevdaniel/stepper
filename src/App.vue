<template>
  <v-app>
    <v-main>
      <Stepper1/>
    </v-main>
  </v-app>
</template>

<script>
import Stepper1 from './components/Stepper1.vue'
export default {
  name: 'App',
  components: {
    Stepper1
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Times, sans-serif;
  text-align: left;
  color: black;
  margin-top: 1px;
}
</style>
