<script>
import User from '@/components/User.vue';
import Products from "@/components/Products.vue";
import Login from "@/components/Login.vue";

export default {
  name: 'App',
  components: {
    Login,
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
    <!--task 6-->
    <Login/>
  </main>
</template>

<style scoped>

</style>
