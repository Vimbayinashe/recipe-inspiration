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

          <b-nav-item-dropdown class="mx-2 mx-md-0" right text="Dinner">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown class="mx-2 mx-md-0" right text="Other Meals">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown class="mx-2 mx-md-0" right text="European">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown class="mx-2 mx-md-0" right text="Asian">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown class="mx-2 mx-md-0" right text="International">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
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