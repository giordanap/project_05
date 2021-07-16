<template>
  <!-- submit receive a method -->
  <!-- The method print to console, but is hidden because submit use get and therefore the memory is refreshed -->
  <!-- with prevent will no longer refresh by default -->
  <form @submit.prevent="processForm">
    
    <!-- in Bootstrap can use mt-5 mb-5 or my-5 -->
    <h2 class="my-5" >Form with Vue.js</h2>

    <input 
      type="text"
      class="form-control my-2"
      placeholder="Input name"
      v-model.trim="task.name"
    >
    <div class="form-check form-check-inline">
      <input 
        type="checkbox" 
        id="check-1 "
        class="form-check-input"
        v-model="task.categories"
        value="javascript"
      >
      <label for="check-1" class="form-check-label"> Javascript </label>
    </div>
    <div class="form-check form-check-inline">
      <input 
        type="checkbox" 
        id="check-1 "
        class="form-check-input"
        v-model="task.categories"
        value="node js"
      >
      <label for="check-1" class="form-check-label"> Node.js </label>
    </div>
    <div class="form-check form-check-inline">
      <input 
        type="checkbox" 
        id="check-1 "
        class="form-check-input"
        v-model="task.categories"
        value="python"
      >
      <label for="check-1" class="form-check-label"> Python </label>
    </div>
    <div class="form-check form-check-inline">
      <input 
        type="checkbox" 
        id="check-1 "
        class="form-check-input"
        v-model="task.categories"
        value="c#"
      >
      <label for="check-1" class="form-check-label"> C# </label>
    </div>

    <div class="mt-2">

      <div class="form-check form-check-inline">
        <input 
          type="radio"
          id="radio-1"
          class="form-check-input"
          v-model="task.state"
          value="urgent"
        >
        <label for="radio-1" class="form-check-label"> Urgent </label>
      </div>
      <div class="form-check form-check-inline">
        <input 
          type="radio"
          id="radio-2"
          class="form-check-input"
          v-model="task.state"
          value="relax"
        >
        <label for="radio-2" class="form-check-label"> Relax </label>
      </div>

    </div>

    <div class="mt-2">
      <input 
        type="number"
        class="form-control"
        v-model.number ="task.number"
      >
    </div>

    <button 
      class="btn btn-dark btn-block mt-2" 
      type="submit"
      :disabled='lockButton'
    >
      Process
    </button>

  </form>
  <hr>
  <p>
    {{ task }}
  </p>
</template>

<script>

export default {
  name: 'Home',
  data() {
    return {
      task: {
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
  },
  computed: {
    lockButton() {
      return this.task.name.trim() === "" ? true : false
    }
  }
}
</script>
