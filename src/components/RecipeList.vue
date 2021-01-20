<template>
  <div>
    <h1>recipes</h1>
    <ul>
      <li v-for="recipe in recipes" :key="recipe.ID">
        {{recipe.Name}}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      recipes: [],
    }
  },
  mounted() {
    axios.get("http://127.0.0.1:3000/recipes")
      .then(response => {
        this.recipes = response.data.data
      })
  }
}
</script>
