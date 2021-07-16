<template>
  <!-- submit receive a method -->
  <!-- The method print to console, but is hidden because submit use get and therefore the memory is refreshed -->
  <!-- with prevent will no longer refresh by default -->
  <form @submit.prevent="processForm">
    
    <!-- in Bootstrap can use mt-5 mb-5 or my-5 -->
    <h1 class="my-5" >Form with Vue.js</h1>
    <Input :task="task"/>
  </form>
  <hr>
  <p>
    {{ task }}
  </p>
</template>

<script>
import Input from '../components/Input.vue'

export default {
  name: 'Home',
  components: {
    Input
  },
  data() {
    return {
      task: {
        id: '',
        name: '',
        categories: [],
        state: '',
        number: 0
      },
      disabled: true
    }
  },
  methods: {
    processForm() {
      // Here send the data
      console.log(this.task)
      // validation to detect empty fields
      if (this.task.name.trim() === "") {
        console.log('empty field')
        return
      }
      // console.log("it is not empty")

      // Here clean the data
      this.task = {
        name: '',
        categories: [],
        state: '',
        number: 0
      }
    }
  }
}
</script>
