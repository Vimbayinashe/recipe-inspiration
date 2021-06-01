/* eslint-disable no-console */
<template>
  <div>
    <div>
      <b-container>
        <b-row>
          <b-col>
            <h1 class="d-block mb-4 mt-5 pt-4 text-center title">What's cooking?</h1>
          </b-col>
        </b-row>
        <b-row align-h="center">
          <b-col class="ml-md-n5" cols="auto">
            <p class="font-italic">
              "Find meal inspiration and delicious recipes from all around the world right here!"
            </p>
          </b-col>
        </b-row>
        <b-row align-h="center" class="my-3">
          <b-col cols="auto">
            <b-img alt="several types of vegetables" fluid rounded src="@/assets/images/vegetables-700.jpg" />
          </b-col>
        </b-row>
        <Recipe :recipe="random" suggestion />
        
      </b-container>     
    </div>
  </div>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
  async asyncData({ $axios }) {
    const allIngredients = await $axios.$get('/list.php?i=list')
    const areas = await $axios.$get('/list.php?a=list')
    const categories = await $axios.$get('/categories.php')
    const random = await $axios.$get('/random.php')

    return {
      allIngredients: allIngredients.meals,
      areas: areas.meals,
      categories: categories.categories,
      random: random.meals[0],
    }
  },
  components: {
    Recipe
  }
}
</script>
