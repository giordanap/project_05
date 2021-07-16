<template>
  <NavBar />
  <!-- use container class for fit to the form -->
  <div class="container">
    <router-view/>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'

export default {
  components: {
    NavBar
  }
}
</script>
