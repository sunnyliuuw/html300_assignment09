<template>
  <div>
    <!-- nav bar container -->
    <div class="container bg-white">
      <!-- nav bar -->
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <ul class="nav">
          <li class="nav-item bg-primary">
            <!-- nuxt router link -->
            <nuxt-link to="/" class="nav-link text-white">Home</nuxt-link>
          </li>
          <li class="nav-item bg-success">
            <nuxt-link to="/about" class="nav-link text-white">About</nuxt-link>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<style>

</style>
