<script setup>

</script>

<template>
  <div>
    <header>
      <nav class="navbar bg-danger ">
        <div class="container d-flex justify-content-center">
          <router-link class="navbar-brand" to="/">
            <img src="./assets/pokeball.png" alt="" width="60" height="60">
          </router-link>
        </div>
      </nav>  

    </header>
    
  <div class="main">
    <router-view></router-view>
  </div>

  </div>
</template>

<style scoped>


</style>
