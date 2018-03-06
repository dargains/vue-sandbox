<template lang="html">
  <div>
    <router-link to="/products">Back to all</router-link>
    <h2><strong>{{product.name}}</strong></h2>
    <img :src="product.image">
    <p>{{product.description}}</p>
    <strong>Price: ${{product.price}}</strong>
    <div class="">
      <button type="button" name="button">Add to cart</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "product",
  data() {
    return {
      product: {}
    }
  },
  created() {
    let id = this.$route.params.id;
    $.getJSON(`https://hplussport.com/api/products/id/${id}`)
    .done(data => {
      this.product = data[0];
    })
  }
}
</script>

<style lang="css" scoped>
  img {
    width: 700px;
    height: 700px;
  }
</style>
