<template>
  <div class="section">
    <div class="container">
      <div class="columns">
        <div class="column is-6">
          <div class="image is-2by2">
            <img  :src="product.imageUrl">
          </div>
        </div>
        <div class="column is-5 is-offset-1">
          <div class="title is-2">{{ product.name }}</div>
          <p class="title is-3 has-text-muted">€ {{ product.price }}</p>
          <hr>
          <br>
          <p class="">
            <i class="fa fa-star title is-5" style="color:#ed6c63"></i>
            <i class="fa fa-star title is-5" style="color:#ed6c63"></i>
            <i class="fa fa-star title is-5" style="color:#ed6c63"></i>
            <i class="fa fa-star title is-5"></i>
            <i class="fa fa-star title is-5"></i>
            &nbsp; &nbsp;
            <strong>41 recensioni</strong>
            &nbsp; &nbsp;
          </p>
          <br>
          <p>{{ product.description }}
          </p>
          <br>
          <br>
          <p class="">
            <a href="#">
              <i class="fa fa-minus cart-icon"></i>
            </a>
            &nbsp;
            <input type="text" name="" class="input has-text-centered" value="1" style="width:40px;">
            &nbsp;
            <a href="#">
              <i class="fa fa-plus cart-icon"></i>
            </a>
            &nbsp; &nbsp; &nbsp;
            <a class="button is-primary">Add to cart</a>
          </p>
          <br>
        </div>
      </div>
    </div>
          <div class="links">
        <nuxt-link to="/prodotti"  class="button--green">Torna a prodotti</nuxt-link>
        <nuxt-link to="/"  class="button--green">Torna alla Home Page</nuxt-link>
      </div>
  </div>
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
body {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
}
.has-text-muted {
  color: #95A5A6;
}
.fa {
  font-size:10px;
  padding-top:3px;
  color: #95A5A6;
}
.panel-block-item {
  display: inline-block;
  color: #95A5A6;
  font-weight: bold;
  padding: 0 10px;
}
.cart-icon {
  padding-top:10px;
}
.product-header {
  background-color:#fafafa;
}


.links
{
  padding-top: 15px;
}

</style>
