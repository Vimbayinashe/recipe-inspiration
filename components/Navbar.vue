<template>
  <div>
    <b-navbar
      fixed="top"
      toggleable="md"
      type="dark"
      variant="info"
    >
      <b-navbar-brand to="/">
        <b-icon aria-hidden="" icon="house-fill" variant="light"/>
        <span class="sr-only">Home</span>
      </b-navbar-brand>
      <b-navbar-toggle target="options" />
      <b-collapse id="options" is-nav>
        <b-navbar-nav class="ml-auto">

          <b-nav-item-dropdown class="mx-2" right text="Dinner">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown right text="Other Meals">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown right text="European">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown right text="Asian">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown right text="International">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-form>
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
      dinnerOptions: [
        'Beef',
        'Chicken',
        'Goat',
        'Lamb',
        'Pasta',
        'Pork',
        'Seafood',
        'Vegan',
        'Vegetarian',
        'Variety'
      ]
    }
  }
}
</script>

<style scoped>
#options >>> .nav-link {
  color: white;
}

#options >>> .nav-link>span:hover {
  font-size: 101%;
  text-decoration: underline;
}
</style>