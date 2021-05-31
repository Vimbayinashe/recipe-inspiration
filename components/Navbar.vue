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
              @click="openCategory(option)"
              :key="option" 
              href="#" 
              v-for="option in dinner"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="Other Meals">
            <b-dropdown-item 
              @click="openCategory(option)"
              :key="option" 
              href="#" 
              v-for="option in otherMeals"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="Asian">
            <b-dropdown-item 
              @click="openCategory(option)"
              :key="option" 
              href="#" 
              v-for="option in asian"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="European">
            <b-dropdown-item 
              @click="openCategory(option)"
              :key="option" 
              href="#" 
              v-for="option in european"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" text="International">
            <b-dropdown-item 
              @click="openCategory(option)"
              :key="option" 
              href="#" 
              v-for="option in international"
            >
              {{ option }}
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
      asian: [
        "Indian",
        "Japanese",
        "Malaysian",
        "Chinese",
        "Thai",
        "Vietnamese"
      ],
      dinner: [
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
      european: [
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
      international: [
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
      otherMeals: ["Breakfast", "Dessert", "Side", "Starter"]
    }
  },
  methods: {
    openCategory(category) {
      console.log("open category ", category);
      this.$router.push(`category/${category.toLowerCase()}`)
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