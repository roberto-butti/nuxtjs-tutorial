<template>
  <section class="section main">
    <div class="box">
      <div class="title">Elenco prodotti ({{ howmany }})</div>
    </div>
    <div class="box">
      <article class="media" v-for="product in products">
        <div class="media-left">
          <figure class="image is-64x64">

            <img :src="product.thumbnailUrl" :alt="product.name" />
          </figure>
        </div>
        <div class="media-content">
          <div class="content">
            <p>

               <nuxt-link :to="{ name: 'prodotto-slug', params: { slug: product.slug } }">{{ product.name }}</nuxt-link>
              <small> €{{ product.price }}</small>
              <br> {{ product.description }}
            </p>
          </div>
          <nav class="level">
            <div class="level-left">
              <a class="level-item">
                <span class="icon is-small">
                  <i class="fa fa-reply"></i>
                </span>
              </a>
              <a class="level-item">
                <span class="icon is-small">
                  <i class="fa fa-retweet"></i>
                </span>
              </a>
              <a class="level-item">
                <span class="icon is-small">
                  <i class="fa fa-heart"></i>
                </span>
              </a>
            </div>
          </nav>
        </div>
      </article>
    </div>
    <div class="links">
      <nuxt-link to="/" class="button--green">Torna alla home</nuxt-link>
    </div>
  </section>
</template>

<script>
import products from '~/static/products-list.json'

export default {
  asyncData (context) {
    var howmany = Object.keys(products).length
    return {
      products: products,
      howmany: howmany,
      headtitle: 'Elenco prodotti'
    }
  },
  head () {
    return {
      title: this.headtitle + '(' + this.howmany + ' products)'
    }
  }
}
</script>

<style scoped>
body {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}

.section.main {
  background-color: #f5f8fa;
}
.card-header {
    background-image: url("http://placehold.it/600x200");
    background-position: 0 50%;
    background-size: 100% auto;
    border-bottom: 1px solid #e1e8ed;
    border-radius: 4px 4px 0 0;
    height: 95px;
    width: 100%;
}
.card-content {
    padding: 0px;
}
.card-avatar {
  background-color: #fff;
  border-radius: 6px;
  display: inline-block !important;
  float: left;
  margin: -30px 5px 0 8px;
  max-width: 100%;
  padding: 1px;
  vertical-align: bottom;
}
.card-avatar-img {
  border: 2px solid #fff;
  border-radius: 7px;
  box-sizing: border-box;
  color: #fff;
  height: 72px;
  width: 72px;
}
.card-user {
    margin: 5px 0 0;
}
.card-user-name{
    font-size: 18px;
    font-weight: 700;
    line-height: 21px;
}
.card-user-name a{
    color: inherit !important;
}
.card-stats {
    margin-left: 11px;
    padding: 10px 0;
}
.card-stats-list {
    box-sizing: border-box;
    display: table;
    margin: 0;
    min-width: 100%;
    padding: 0;
    table-layout: auto;
}
ul.card-stats-list {
    list-style: outside none none;
    margin: 0;
    padding: 0;
}
.card-stats-item {
    display: table-cell;
    padding: 0;
    vertical-align: top;
}
.card-stats-item a:hover {
    text-decoration: none;
}
.card-stats-val {
    display: block;
    font-size: 18px;
    font-weight: 500;
    transition: color 0.15s ease-in-out 0s;
}
.card-stats-key {
    color: #8899a6;
    font-size: 10px;
    letter-spacing: 0.02em;
    overflow: hidden;
    text-transform: uppercase;
    transition: color 0.15s ease-in-out 0s;
}
.spacer {
  height:20px;
}

.trending .trend-title {
  padding-bottom: 10px;
}

.trending .trend-hashtag {
  padding-bottom: 8px;
}

.has-text-muted {
  color: #95A5A6;
}

.fa {
  font-size: 10px;
  padding-top: 3px;
  color: #95A5A6;
}

.panel-block-item {
  display: inline-block;
  color: #95A5A6;
  font-weight: bold;
  padding-right: 10px;
}

.panel-block-item .tag,
.panel-block-item .button {
  color: #95A5A6;
  font-weight: bold;
}

.panel-block-item.is-right {
  display: inline-block;
  color: #95A5A6;
  font-weight: bold;
  float: right;
}

.panel-block-item .likes {
  padding-right: 25px;
}

.panel-block-item .likes .fa,
.panel-block-item .comments .fa {
  font-size: 15px;
  margin-top: -2px;
}

.avatar {
  border-radius: 42px;
  margin-right: 10px;
  height: 42px;
  width: 42px;
  padding: 2px;
  border: 1px solid #dbdbdb;
}

.timestamp {
  color: #95A5A6;
  font-weight: bold;
}

.links {
  padding-top: 15px;
}
</style>