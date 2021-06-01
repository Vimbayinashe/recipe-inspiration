<template>
  <b-container>
    <b-row>
      <b-col>
        <h1 class="d-block mb-4 mt-5 pt-4 text-center" v-if="recipe">
          {{ recipe.meals[0].strMeal }}
        </h1>
      </b-col>
    </b-row>
    <Recipe :recipe="recipe.meals[0]" v-if="recipe"/>
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
      recipe: ''
    }
  },
  async fetch() {
    this.recipe = await this.$axios.$get(`/api/lookup.php?i=${this.$route.params.id}`)
  },
  mounted() {
    this.$fetch()
  }
}
</script>