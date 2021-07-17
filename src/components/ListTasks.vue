<template>
    {{tasks}}
  <table class="table">
  <thead>
    <tr>
        <th scope="col">#</th>
        <th scope="col">Name</th>
        <th scope="col">Categories</th>
        <th scope="col">State</th>
        <th scope="col">Number</th>
        <th scope="col">Action</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item in tasks" :key="item.id">
        <th scope="row">{{item.id}}</th>
        <td>{{item.name}}</td>
        <td >
          <span v-for="(cat, index) in item.categories" :key="index">
              {{cat}}
          </span>
        </td>
        <td>{{item.state}}</td>
        <td>{{item.number}}</td>
        <td>Action</td>
    </tr>
  </tbody>
</table>
</template>

<script>
import {mapState} from 'vuex'

export default {
    computed: {
        ...mapState(['tasks'])
    }
}
</script>
