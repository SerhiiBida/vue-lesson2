<script>
export default {
  name: 'Product',
  data() {
    return {
      product: {
        id: 1,
        name: 'Ноутбук 1',
        price: 400
      }
    }
  },
  watch: {
    // 11. Використовуйте watcher для відстеження змін у реактивному об’єкті та виведення повідомлення про це.
    product: {
      handler(newProduct){
        alert(`New: ${JSON.stringify(newProduct)}`);
      },
      deep: true
    },
    // 12. Використовуйте watcher для відстеження змін однієї властивості у реактивному об’єкті та виведення повідомлення про це.
    'product.name': {
      handler(newName, oldName){
        alert(`New: ${newName}\nOld: ${oldName}`);
      }
    }
  }
}
</script>

<template>
  <section>
    <!--11. Використовуйте watcher для відстеження змін у реактивному об’єкті та виведення повідомлення про це.-->
    <p>
      <label>
        ID:
      </label>
      <input v-model="product.id" type="number" name="id" id="id">
    </p>
    <!--12. Використовуйте watcher для відстеження змін однієї властивості у реактивному об’єкті та виведення повідомлення про це.-->
    <p>
      <label>
        Name:
      </label>
      <input v-model="product.name" type="text" name="name" id="name">
    </p>
  </section>
</template>

<style scoped>

</style>