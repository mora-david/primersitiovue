<template>
    
    
    
<div class="card" style="height:100px">
  <div class="card-header">
    <h1>{{producto1.name}}</h1>
  </div>
  <div class="card-body " style="height:100px">
    <blockquote class="blockquote mb-0">
      <img :src="producto1.image" alt="" width="300" height="500">
      <div>
      <a :href="producto1.url"><h2>sitio</h2></a>
      </div>
      <footer class="blockquote-footer"> <cite title="Source Title"> {{producto1.description}}</cite></footer>
    </blockquote>
  </div>
</div>


</template>

<script>
export default {
  props: ['producto1']
}
</script>