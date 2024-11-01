<template>
  <nav class="navbar navbar-expand-lg maroon-color bg-transparent top-0 position-absolute">
    <div class="container-fluid">
      <a class="navbar-brand mx-3" href="#">
        <img src="/favicon.png" width="40px" alt="medna">
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Contact</a>
          </li>
          <li class="nav-item">
            <div class="btn" style="background-color:maroon !important; color: #FFE3BC !important" @click="$parent.pdf">Create PDF</div>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import App from "../App";
export default {
  name: "TheNavbar",
  methods:{

  }
}
</script>

<style scoped>

</style>