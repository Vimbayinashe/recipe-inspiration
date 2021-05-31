<template>
  <b-container>
    <h1 class="d-block mb-4 mt-5 pt-4 text-center">{{ title }}</h1>

    <b-row align-h="around">
      <b-col cols="auto" :key="meal.idMeal" v-for="meal in category.meals">
        <b-card 
          class="my-4"
          :img-alt="'a picture of ' + meal.strMeal"
          img-bottom
          :img-src="meal.strMealThumb"
          style="width: 18em;"
        >
          <b-card-title @click="openRecipe(meal.idMeal)">
            <NuxtLink :to="`/recipe${meal.meal.idMeal}`">
              {{ meal.strMeal }}
            </NuxtLink>
          </b-card-title>
        </b-card>
      </b-col>
    </b-row>
    
    <div>
      {{ category }}
    </div>
  </b-container>
</template>

<script>
export default {
  computed: {
    title() {
      return (this.$route.params.category.slice(0, 1)).toUpperCase() + this.$route.params.category.slice(1)
    }
  },
  data() {
    return {
      category: ''
    }
  },
  async fetch(){
    this.category = await this.$axios.$get(`/filter.php?c=${this.$route.params.category}`)
    console.log(this.category);
  },
  methods: {
    openRecipe(id) {
      console.log("Open recipe with ID: ", id);
    }
  },
  mounted() {
    console.log(this.$route.params.category);
    this.$fetch()
  }
}
</script>

<style scoped>
  .card-title {
    min-height: 56px;
  }
</style>