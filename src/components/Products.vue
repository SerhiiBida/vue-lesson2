<script>
export default {
  name: 'Products',
  emits: ['changeTitle'],
  data() {
    return {
      products: [
        {id: 1, name: 'Ноутбук 1', price: 400},
        {id: 2, name: 'ПК 1', price: 500},
        {id: 3, name: 'Ноутбук 2', price: 200},
        {id: 4, name: 'ПК 2', price: 600},
        {id: 5, name: 'Ноутбук 3', price: 700},
        {id: 6, name: 'ПК 3', price: 125},
        {id: 7, name: 'Ноутбук 4', price: 350},
        {id: 8, name: 'ПК 4', price: 90},
      ],
      title: 'App 2'
    }
  },
  methods: {
    // 4. Створіть метод для фільтрації масиву об'єктів за деяким критерієм.
    productsFilter() {
      return this.products.filter((product) => {
        return product.price > 100 && product.price < 600;
      });
    }
  },
  computed: {
    // 7. Створіть обчислювальну властивість для виведення даних, обчислених на основі інших реактивних даних.
    averagePrice() {
      const products = this.productsFilter();

      const sum = products.reduce((sum, product) => sum + product.price, 0);

      return sum / products.length;
    }
  }
}
</script>

<template>
  <section>
    <div class="products">
      <article v-for="product in productsFilter()" :data-product-id="product.id">
        <p>
          {{ product.name }} - {{ product.price }}$
        </p>
      </article>
    </div>
    <p>
      Середня ціна: {{ averagePrice }}$
    </p>
    <!--5. Використайте метод для обробки події кліку, який змінює стан інших компонентів.-->
    <button @click="$emit('changeTitle', title)">
      Змінити заголовок
    </button>
  </section>
</template>

<style scoped>

</style>