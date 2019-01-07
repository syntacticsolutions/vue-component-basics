<template>
  <div id="app">
    <UserAdminDashboard />
  </div>
</template>

<script>
import UserAdminDashboard from './components/UserAdminDashboard.vue'

export default {
  name: 'app',
  components: {
    UserAdminDashboard
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
