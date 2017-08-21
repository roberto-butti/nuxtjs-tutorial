<template>
  <section class="container">
    <div>
      <h1 class="title">
        {{ product.name }}
      </h1>
      <h2 class="description">
        {{ product.description}}
      </h2>
      <div class="price">{{ product.price }} €</div>
      <img width="400" :src="product.imageUrl">
      <div class="links">
        <nuxt-link to="/prodotti"  class="button--green">Torna a prodotti</nuxt-link>
        <nuxt-link to="/"  class="button--green">Torna alla Home Page</nuxt-link>
      </div>
    </div>
  </section>

    
</template>


<script>
import products from '~/static/products-list.json'

export default {
  asyncData (context) {
    console.log(context.params.slug)
    console.log(products[context.params.slug])
    return { slug: context.params.slug, product: products[context.params.slug] }
  },
  head () {
    return {
      title: 'Prodotto - ' + this.product.name,
      meta: [
        { hid: 'description', name: 'description', content: 'DEscrizione prodotto' }
      ]
    }
  }

}
</script>

<<style scoped>
.container
{
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title
{
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
.subtitle
{
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.description
{
  font-weight: 300;
  font-size: 18px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}
.price
{
  font-weight: 600;
  font-size: 32;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links
{
  padding-top: 15px;
}

</style>
