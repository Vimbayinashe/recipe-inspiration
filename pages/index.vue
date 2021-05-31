/* eslint-disable no-console */
<template>
  <div>
    <div>
      <Navbar :areas="areas" :categories="categories" />
      <h1 class="d-block mb-4 mt-5 pt-4 title">What's cooking?</h1>
      <p>
        <i>
          "Find meal inspiration and delicious recipes from all around the world right here!"
        </i>
      </p>
      <b-container>
        <div>
          {{ categories[0] }}
        </div>

      </b-container>
      
     
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
export default {
  async asyncData({ $axios }) {
    const allIngredients = $axios.$get('/list.php?i=list')
    const areas = await $axios.$get('/list.php?a=list')
    const categories = await $axios.$get('/categories.php')
    const random = await $axios.$get('/random.php')

    return {
      allIngredients: allIngredients.meals,
      areas: areas.meals,
      categories: categories.categories,
      random,
    }
  },
  components: {
    Navbar
  }
}
</script>
