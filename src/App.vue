<script>
import User from '@/components/User.vue';
import Products from "@/components/Products.vue";

export default {
  name: 'App',
  components: {
    User,
    Products
  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <main>
    <!--tasks 1-3-->
    <User/>
    <!--task 4-->
    <Products/>
  </main>
</template>

<style scoped>

</style>
