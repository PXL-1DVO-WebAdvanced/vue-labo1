<template>
<nav class="navbar navbar-expand-lg bg-dark" data-bs-theme="dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Vue.js labo</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarText" aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarText">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Products</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">About</a>
        </li>
      </ul>
      <span class="navbar-text">
        <button type="button" class="btn btn-light" @click="logout()">{{ username }}</button>
      </span>
    </div>
  </div>
</nav>
</template>
<script>
export default {
    props: [
        'username'
    ],
    emits: [
        'userLogout'
    ],
    methods: {
        logout() {
            this.$emit('userLogout')
        }
    }
}
</script>
<style lang="scss">
    
</style>