<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <router-link to="/admin">
      <h2>Admin</h2>
    </router-link>
    <router-link to="/user">
      <h2>User</h2>
    </router-link>
    <router-link to="/login"><h2>Login</h2></router-link>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
