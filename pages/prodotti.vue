<template>
  <section class="container">
    <div>
      <h1 class="title">
        Elenco prodotti
      </h1>
      <div class="products">
        <ul>
          <li v-for="product in products">
            <nuxt-link :to="{ name: 'prodotto-slug', params: { slug: product.slug } }">{{ product.name }}</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="links">
        <nuxt-link to="/" class="button--green">Torna alla home</nuxt-link>
      </div>
  
    </div>
  </section>
</template>

<script>
import products from '~/static/products-list.json'

export default {
  data () {
    return { products }
  },
  head: {
    title: 'Elenco di prodotti'
  }
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.links {
  padding-top: 15px;
}
</style>