<template>
  <b-container>
    <b-row>
      <b-col>
        <h1 class="d-block mb-4 mt-5 pt-4 text-center">
          {{ recipe.meals[0].strMeal }}
        </h1>
      </b-col>
    </b-row>
    <Recipe :recipe="recipe.meals[0]"/>
  </b-container>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
  components: {
    Recipe
  },
  data() {
    return {
      recipe: null
    }
  },
  async fetch() {
    this.recipe = await this.$axios.$get(`/lookup.php?i=${this.$route.params.id}`)
    console.log(this.recipe)
  },
  mounted() {
    this.$fetch()
  }
}
</script>