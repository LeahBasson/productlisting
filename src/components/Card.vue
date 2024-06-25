<template>

 <div class="card">
  <div class="card-header">

    <slot name="cardHeader"></slot>

  </div>
  <div class="card-body">
    
    <slot name="cardBody"></slot>

  </div>
</div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.card{
  width: 18rem;
}

</style>
