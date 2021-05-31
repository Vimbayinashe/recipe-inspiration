<template>
  <div>
    <b-row align-h="center" class="mt-5">
      <b-col cols="auto">
        <h3>Would you like to try {{ recipe.strMeal }}?</h3>
      </b-col>
    </b-row>
    <b-row align-h="center">
      <b-col cols="auto">
        <!-- restrict image size -->
        <b-img :alt="'a picture of ' + recipe.strMeal" fluid :src="recipe.strMealThumb" />
      </b-col>
    </b-row>
    <b-row class="mt-4">
      <b-col cols="6" offset-md="3">
        <h4>Ingredients</h4>
        <ol>
          <li v-if="recipe.strMeasure1 && recipe.strIngredient1">
            {{ recipe.strMeasure1 }} {{ recipe.strIngredient1}}
          </li>
          <li v-if="recipe.strMeasure2 && recipe.strIngredient2">
            {{ recipe.strMeasure2 }} {{ recipe.strIngredient2}}
          </li>
          <li v-if="recipe.strMeasure3 && recipe.strIngredient3">
            {{ recipe.strMeasure3 }} {{ recipe.strIngredient3}}
          </li>
          <li v-if="recipe.strMeasure4 && recipe.strIngredient4">
            {{ recipe.strMeasure4 }} {{ recipe.strIngredient4}}
          </li>
          <li v-if="recipe.strMeasure5 && recipe.strIngredient5">
            {{ recipe.strMeasure5 }} {{ recipe.strIngredient5}}
          </li>
          <li v-if="recipe.strMeasure6 && recipe.strIngredient6">
            {{ recipe.strMeasure6 }} {{ recipe.strIngredient6}}
          </li>
          <li v-if="recipe.strMeasure7 && recipe.strIngredient7">
            {{ recipe.strMeasure7 }} {{ recipe.strIngredient7}}
          </li>
          <li v-if="recipe.strMeasure8 && recipe.strIngredient8">
            {{ recipe.strMeasure8 }} {{ recipe.strIngredient8}}
          </li>
          <li v-if="recipe.strMeasure9 && recipe.strIngredient9">
            {{ recipe.strMeasure9 }} {{ recipe.strIngredient9}}
          </li>
          <li v-if="recipe.strMeasure10 && recipe.strIngredient10">
            {{ recipe.strMeasure10 }} {{ recipe.strIngredient10}}
          </li>
          <li v-if="recipe.strMeasure11 && recipe.strIngredient11">
            {{ recipe.strMeasure11 }} {{ recipe.strIngredient11}}
          </li>
          <li v-if="recipe.strMeasure12 && recipe.strIngredient12">
            {{ recipe.strMeasure12 }} {{ recipe.strIngredient12}}
          </li>
          <li v-if="recipe.strMeasure13 && recipe.strIngredient13">
            {{ recipe.strMeasure13 }} {{ recipe.strIngredient13}}
          </li>
          <li v-if="recipe.strMeasure14 && recipe.strIngredient14">
            {{ recipe.strMeasure14 }} {{ recipe.strIngredient14}}
          </li>
          <li v-if="recipe.strMeasure15 && recipe.strIngredient15">
            {{ recipe.strMeasure15 }} {{ recipe.strIngredient15}}
          </li>
          <li v-if="recipe.strMeasure16 && recipe.strIngredient16">
            {{ recipe.strMeasure16 }} {{ recipe.strIngredient16}}
          </li>
          <li v-if="recipe.strMeasure17 && recipe.strIngredient17">
            {{ recipe.strMeasure17 }} {{ recipe.strIngredient17}}
          </li>
          <li v-if="recipe.strMeasure18 && recipe.strIngredient18">
            {{ recipe.strMeasure18 }} {{ recipe.strIngredient18}}
          </li>
          <li v-if="recipe.strMeasure19 && recipe.strIngredient19">
            {{ recipe.strMeasure19 }} {{ recipe.strIngredient19}}
          </li>
          <li v-if="recipe.strMeasure20 && recipe.strIngredient20">
            {{ recipe.strMeasure20 }} {{ recipe.strIngredient20}}
          </li>
        </ol>
      </b-col>
    </b-row>
    <b-row class="mt-2">
      <b-col>
        <h4>Instructions</h4>
        <p>{{ recipe.strInstructions }}</p>
      </b-col>
    </b-row>

    <b-row class="mt-2">
      <b-col>
        <h4>Watch recipe:</h4>
        <b-embed 
          allowfullscreen 
          :src="recipe.strYoutube" 
          type="iframe"
        />
      </b-col>
    </b-row>
    <b-row class="mt-3">
      <b-col>
        <span class="h5">Source: </span>{{ recipe.strSource }}
      </b-col>
    </b-row>
</div>
</template>

<script>
export default {
  props: {
    recipe: Object
  }
}
</script>