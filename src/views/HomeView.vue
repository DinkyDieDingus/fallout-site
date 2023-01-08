<script setup>
import Logo from '../components/Logo.vue'
import Link from '../components/Link.vue'
import axios from "axios"
</script>
<script>
export default {
  data() {
    return {
      linkData: {}
    }
  },
  mounted() {
    axios.get('/links.json').then((response) => {this.linkData=response.data})
  }
}
</script>

<template>
  <main>
    <Logo />
    <div class="links">
      <Link v-for="category in linkData.categories" :name="category.title" :links="category.links"/>
    </div>
  </main>
</template>

<style scoped>
  .links {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    /*
    gap: 40pt;
    */
  }
</style>