<template>
  <div class="root">
    <div class="centering">
      <h1>Tables</h1>
      <div class="inp">
        <input type="text" v-model="searchTable" />
        <p>
          Всего товара: {{ products.length }}, совпадений:{{ findTable.length }}
        </p>
      </div>
    </div>
    <ul class="flex-box">
      <p v-for="(product, index) in findTable" :key="index">
        <Card
          :title="product.title"
          :price="product.price"
          :imgUrl="product.imgUrl"
          :count="product.count"
        />
      </p>
    </ul>
  </div>
</template>

<script>
import Card from '@/components/Task3/SupportVue3.vue'

export default {
  name: 'MainVue3',
  components: { Card },
  data() {
    return {
      searchTable: '',
      products: [
        {
          title: 'Стол Jim',
          price: 19999,
          imgUrl:
            'https://ogogo.ru/images/products/9691/ac2eb2ae36f0264d2b8649117690e5e6.webp',
          count: 0,
        },
        {
          title: 'Стол Monako',
          price: 17199,
          imgUrl:
            'https://nizhniy-tagil.unik-mebel.ru/upload/resize_cache/webp/upload/iblock/705/7050c3023b11f23a6f8ef9e3a02863dc.webp',
          count: 20,
        },
        {
          title: 'Стол с двумя ящиками Кварт MD 768',
          price: 10999,
          imgUrl:
            'https://hoff.ru/upload/iblock/1cc/1ccb33b50e3e9cfa08629bf455e41855.jpg',
          count: 23,
        },
      ],
    }
  },
  computed: {
    findTable() {
      const ans = []
      const name = this.searchTable.toLowerCase()

      this.products.forEach(product => {
        if (product.title.toLowerCase().includes(name)) {
          ans.push(product)
        }
      })
      console.log(ans.length)
      return ans
    },
  },
  watch: {},
  methods: {},
}
</script>
<style>
.flex-box {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 2rem;
}
.centering {
  display: grid;
  place-content: center;
}
h1 {
  text-align: center;
}
input {
  text-align: center;
}
.inp {
  display: grid;
  place-content: center;
}
</style>
