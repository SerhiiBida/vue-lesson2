<script>
export default {
  name: "Posts",
  data(){
    return {
      title: 'JSON',
      data: null
    }
  },
  methods: {
    async getData() {
      const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');

      this.data = await response.json();
    }
  },
  computed: {
    // 9. Створіть computed property, яке комбінує дані відповіді від HTTP запиту та з рекативною змінною.
    dataOutput() {
      return `${this.title}: ${this.data ? JSON.stringify(this.data) : 'Чекаємо...'}`;
    }
  },
  mounted() {
    // Компонент Post примонтирован на страницу
    this.getData();
  }
}
</script>

<template>
  <section>
    <p>
      {{ dataOutput }}
    </p>
  </section>
</template>

<style scoped>

</style>