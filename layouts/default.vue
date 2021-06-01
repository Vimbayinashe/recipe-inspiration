<template>
  <div>
    <Navbar />
    <Nuxt />
    <div class="bg-info fixed-bottom mt-4 py-2">
      <footer class="container text-white">
        &#169; What's cooking Inc.
      </footer>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
export default {
  components: {
    Navbar
  }
}
</script>
