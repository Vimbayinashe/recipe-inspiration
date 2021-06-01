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
          <b-card-title>
            <NuxtLink :to="`/recipes/${meal.idMeal}`">
              {{ meal.strMeal }}
            </NuxtLink>
          </b-card-title>
        </b-card>
      </b-col>
    </b-row>
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
    if(this.$route.query.type === "food") {
      this.category = await this.$axios.$get(`/filter.php?c=${this.$route.params.category}`)
    } else if (this.$route.query.type === "area") {
      this.category = await this.$axios.$get(`/filter.php?a=${this.$route.params.category}`)
    }
  },
  mounted() {
    this.$fetch()
  }
}
</script>

<style scoped>
  a {
    color: #212529;
  }

  a:hover{
    text-decoration: none;
  } 

  .card-title {
    min-height: 56px;
  }
</style>