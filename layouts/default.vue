<template>
  <div id="app">
    <Nav />

    <div class="container py-4">
      <Nuxt />
    </div>
  </div>
</template>

<script>
import Nav from '@/components/Nav'

export default {
  components: {
    Nav
  }
}
</script>
