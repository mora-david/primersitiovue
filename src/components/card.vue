<template>

<div class="card text-white bg-secondary mb-3 d-flex justify-content-center container" style="width:300px; height:600px; 18rem; margin:10px">
  <div class="card-header">{{product1.name}}</div>
  <div class="card-body" style="overflow:scroll ">
    <h5 class="card-title">{{product1.description}}</h5>
    <a :href="'/product/'+product1.uuid"><h2>sitio</h2></a>
  </div>
  <div style="overflow:scroll">
  <img width="200" height="600" :src="product1.image">
  </div>
  <div>
</div>





</div>
</template>


<script>
export default {
  props: ['product1']
}
</script>