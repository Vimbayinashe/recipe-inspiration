<template>
  <div>
    <b-navbar
      fixed="top"
      toggleable="md"
      type="dark"
      variant="info"
    >
      <b-navbar-brand>
        <NuxtLink to="/">
          <b-icon aria-hidden="" icon="house-fill" variant="light"/>
          <span class="sr-only">Home</span>
        </NuxtLink>
      </b-navbar-brand>
      <b-navbar-toggle target="options" />
      <b-collapse id="options" is-nav>
        <b-navbar-nav class="ml-auto">

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="Dinner">
            <b-dropdown-item 
              :key="option.idCategory" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option.strCategory }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="Other Meals">
            <b-dropdown-item 
              :key="option.idCategory" 
              href="#" 
              v-for="option in otherMealOptions"
            >
              {{ option.strCategory }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="European">
            <b-dropdown-item 
              :key="option.strArea" 
              href="#" 
              v-for="option in europeanOptions"
            >
              {{ option.strArea }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="Asian">
            <b-dropdown-item 
              :key="option.strArea" 
              href="#" 
              v-for="option in asianOptions"
            >
              {{ option.strArea }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="International">
            <b-dropdown-item 
              :key="option.strArea" 
              href="#" 
              v-for="option in internationalOptions"
            >
              {{ option.strArea }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-form class="ml-4 ml-md-3 ml-sm-0">
            <b-form-input placeholder="Search" size="sm"/>
            <b-button size="sm" variant="light">
              <b-icon aria-hidden flip-h icon="search" variant="info" />
              <span class="sr-only">Search</span>
            </b-button>
          </b-nav-form>

        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      asianOptions: [],
      dinnerOptions: [],
      europeanOptions: [],
      internationalOptions: [],
      otherMealOptions: []
    }
  },
  mounted() {
    const asian = [
      "Indian",
      "Japanese",
      "Malaysian",
      "Chinese",
      "Thai",
      "Vietnamese"
    ],
    dinner = [
      "Beef",
      "Chicken",
      "Goat",
      "Lamb",
      "Pasta",
      "Pork",
      "Seafood",
      "Vegan",
      "Vegetarian",
      "Miscellaneous"
    ],
    european = [
      "British",
      "Dutch",
      "French",
      "Greek",
      "Irish",
      "Italian",
      "Polish",
      "Portuguese",
      "Spanish"
    ],
    international = [
      "American",
      "Mexican",
      "Canadian",
      "Egyptian",
      "Jamaican",
      "Kenyan",
      "Moroccan",
      "Tunisian",
      "Russian",
      "Turkish"
    ],
    otherMeals = ["Breakfast", "Dessert", "Side", "Starter"]

    if(this.categories.length > 0) {
      this.dinnerOptions = this.categories.filter(category => (
        dinner.includes(category.strCategory)
      ))
      this.otherMealOptions = this.categories.filter(category => (
        otherMeals.includes(category.strCategory)
      ))
    }

    if(this.areas.length > 0) {
      this.asianOptions = this.areas.filter(area => (
        asian.includes(area.strArea)
      ))
      this.europeanOptions = this.areas.filter(area => (
        european.includes(area.strArea)
      ))
      this.internationalOptions = this.areas.filter(area => (
        international.includes(area.strArea)
      ))
    }
  },
  props: {
    areas: Array,
    categories: Array
  }
}
</script>

<style scoped>
  .form-inline > input {
    border-bottom-right-radius: 0;
    border-top-right-radius: 0;
    width: 10em;
  }

  .form-inline > .btn {
    border-bottom-left-radius: 0;
    border-top-left-radius: 0;
  }

  #options >>> .nav-link {
    color: white;
  }

  #options >>> .nav-link>span:hover {
    font-size: 101%;
    text-decoration: underline;
  }
</style>