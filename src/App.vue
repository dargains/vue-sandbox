<template>
  <router-view :products="theProducts" title="Shop our cenas"></router-view>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      theProducts: []
    }
  },
  created: function() {
    $.getJSON('https://hplussport.com/api/products')
      .done(data => {
        this.theProducts = data;
      });
  }
}
</script>
