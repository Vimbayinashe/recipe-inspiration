<template>
  <div>
    <b-navbar
      fixed="top"
      toggleable="md"
      type="dark"
      variant="info"
    >
      <b-navbar-brand to="/">
        Home
      </b-navbar-brand>
      <b-navbar-toggle target="options" />
      <b-collapse id="options">
        <b-navbar-nav class="ml-auto">
          <b-nav-item-dropdown right text="Dinner">
            <b-dropdown-item 
              :key="option" 
              href="#" 
              v-for="option in dinnerOptions"
            >
              {{ option }}
            </b-dropdown-item>
            <b-dropdown-item-button></b-dropdown-item-button>
          </b-nav-item-dropdown>
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