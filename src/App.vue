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
      title: 'App 1'
    }
  },
  methods: {
    // 5. Використайте метод для обробки події кліку, який змінює стан інших компонентів.
    changeTitle(title) {
      this.title = title;
    }
  }
}
</script>

<template>
  <main>
    {{ title }}
    <!--tasks 1-3-->
    <User/>
    <!--task 4-5-->
    <Products @change-title="changeTitle"/>
  </main>
</template>

<style scoped>

</style>
