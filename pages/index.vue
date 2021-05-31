/* eslint-disable no-console */
<template>
  <div>
    <div>
      <Navbar :areas="areas" :categories="categories" />
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

        <b-row align-h="center" class="mt-5">
          <b-col cols="auto">
            <h3>Would you like to try {{ random.strMeal }}?</h3>
          </b-col>
        </b-row>
        <b-row align-h="center">
          <b-col cols="auto">
            <!-- restrict image size -->
            <b-img :alt="'a picture of ' + random.strMeal" fluid :src="random.strMealThumb" />
          </b-col>
        </b-row>
        <b-row class="mt-4">
          <b-col cols="6" offset-md="3">
            <h4>Ingredients</h4>
            <ol>
              <li v-if="random.strMeasure1 && random.strIngredient1">
                {{ random.strMeasure1 }} {{ random.strIngredient1}}
              </li>
              <li v-if="random.strMeasure2 && random.strIngredient2">
                {{ random.strMeasure2 }} {{ random.strIngredient2}}
              </li>
              <li v-if="random.strMeasure3 && random.strIngredient3">
                {{ random.strMeasure3 }} {{ random.strIngredient3}}
              </li>
              <li v-if="random.strMeasure4 && random.strIngredient4">
                {{ random.strMeasure4 }} {{ random.strIngredient4}}
              </li>
              <li v-if="random.strMeasure5 && random.strIngredient5">
                {{ random.strMeasure5 }} {{ random.strIngredient5}}
              </li>
              <li v-if="random.strMeasure6 && random.strIngredient6">
                {{ random.strMeasure6 }} {{ random.strIngredient6}}
              </li>
              <li v-if="random.strMeasure7 && random.strIngredient7">
                {{ random.strMeasure7 }} {{ random.strIngredient7}}
              </li>
              <li v-if="random.strMeasure8 && random.strIngredient8">
                {{ random.strMeasure8 }} {{ random.strIngredient8}}
              </li>
              <li v-if="random.strMeasure9 && random.strIngredient9">
                {{ random.strMeasure9 }} {{ random.strIngredient9}}
              </li>
              <li v-if="random.strMeasure10 && random.strIngredient10">
                {{ random.strMeasure10 }} {{ random.strIngredient10}}
              </li>
              <li v-if="random.strMeasure11 && random.strIngredient11">
                {{ random.strMeasure11 }} {{ random.strIngredient11}}
              </li>
              <li v-if="random.strMeasure12 && random.strIngredient12">
                {{ random.strMeasure12 }} {{ random.strIngredient12}}
              </li>
              <li v-if="random.strMeasure13 && random.strIngredient13">
                {{ random.strMeasure13 }} {{ random.strIngredient13}}
              </li>
              <li v-if="random.strMeasure14 && random.strIngredient14">
                {{ random.strMeasure14 }} {{ random.strIngredient14}}
              </li>
              <li v-if="random.strMeasure15 && random.strIngredient15">
                {{ random.strMeasure15 }} {{ random.strIngredient15}}
              </li>
              <li v-if="random.strMeasure16 && random.strIngredient16">
                {{ random.strMeasure16 }} {{ random.strIngredient16}}
              </li>
              <li v-if="random.strMeasure17 && random.strIngredient17">
                {{ random.strMeasure17 }} {{ random.strIngredient17}}
              </li>
              <li v-if="random.strMeasure18 && random.strIngredient18">
                {{ random.strMeasure18 }} {{ random.strIngredient18}}
              </li>
              <li v-if="random.strMeasure19 && random.strIngredient19">
                {{ random.strMeasure19 }} {{ random.strIngredient19}}
              </li>
              <li v-if="random.strMeasure20 && random.strIngredient20">
                {{ random.strMeasure20 }} {{ random.strIngredient20}}
              </li>
            </ol>
          </b-col>
        </b-row>
        <b-row class="mt-2">
          <b-col>
            <h4>Instructions</h4>
            <p>{{ random.strInstructions }}</p>
          </b-col>
        </b-row>

        <b-row class="mt-2">
          <b-col>
            <h4>Watch recipe:</h4>
            <b-embed 
              allowfullscreen 
              :src="random.strYoutube" 
              type="iframe"
            />
          </b-col>
        </b-row>
        <b-row class="mt-3">
          <b-col>
            <span class="h5">Source: </span>{{ random.strSource }}
          </b-col>
        </b-row>

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

    console.log(random.meals[0]);

    return {
      allIngredients: allIngredients.meals,
      areas: areas.meals,
      categories: categories.categories,
      random: random.meals[0],
    }
  },
  components: {
    Navbar
  }
}
</script>
