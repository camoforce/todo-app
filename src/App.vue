<template>
  <div id="app">
    <img class="vue-logo" alt="Vue logo" src="./assets/logo.png">
    
    <div class="todo">
      <h1>Vue To Do</h1>
      <task></task>
    </div>
      
  </div>
</template>

<script>
import task from '@/components/Task';

export default {
  name: 'App',
  components: {
    task,
  },
  methods: {
    
  }
}
</script>

<style lang="sass">
#app 
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50
  margin-top: 50px

.vue-logo
  width: 100px

</style>
