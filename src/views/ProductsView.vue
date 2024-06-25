<template>
  <div class="container">
      <div class="row">
          <h2>Products</h2>
      </div>
      <div class="row gap-2 justify-content-center" v-if="products?.length">
          <Card v-for="product in products" :key="product.id">
              <template #cardHeader>
                  <img :src="product.img_url" :alt="product.productName" loading="lazy" class="img-fluid">
              </template>
              <template #cardBody>
                  <h5 class="card-title">{{ product.productName }}
                  </h5>
                  <p class="lead">{{ product.Material }}</p>
                  <p class="shadow">R {{ product.Amount }}</p>
              </template>
          </Card>
      </div>
      <div v-else class="d-flex justify-content-center">
          <div class="spinner-border" role="status">
          </div>
      </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue';
export default {
  components: {
      Card
  },
  computed: {
      products() {
          return this.$store.state.products
      }
  },
  beforeCreate() {
    console.log("Before create")
  },
  created(){
    alert("Created") //Will only use this one
  },
  beforeMount() {
    alert("Before Mount")
  },
  mounted() {
      this.$store.dispatch('fetchProducts') //And this one
  },
  unmounted(){
    alert('Unmounted')
  }

}
</script>
<style scoped>
img{
    aspect-ratio: 1;
    object-fit: cover;
    object-position: center;
}
</style>