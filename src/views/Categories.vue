<template>
<div>



      <div class="espacio col-sm-12">
          <h2>Categories</h2>
          <div class="container mt-2 espacio2">
              <div class="row">
                <input class="input pl-0 pr-0 font-weight-bold" type="text" placeholder="Browse categories">
                <span class="icon-search pl-0 pr-0 text-right lupa"></span>
              </div>
            </div>
      </div>


 <div class="container d-flex justify-content-center flex-row bd-highlight mb-3">
  <div class="row" style="width:40%">
    <div class="col-sm" v-for="categorie in categories.categories" :key="categorie.id">
      <div class="card-img-top mx-auto d-block" style="width:105px; height:210px; border:solid; margin:10px; background-image:url('https://contenidos.enter.co/custom/uploads/2019/09/Marvel-DImension-of-Heroes.jpg')">
<p class="p-2 bd-highlight"><i class="fas fa-volume-down icon"></i></p>
                <p class="p-2 bd-highlight" style="color:yellow; font-size:1.2rem">{{categorie.name}}</p>
                <a class="p-2 bd-highlight" style="color:cyan; font-size:1.2rem"  :href="'category/' + categorie.uuid">Productos</a>
                                <p class="p-2 bd-highlight" style="color:yellow; font-size:1.2rem">listening</p>

                 </div>
</div>
    </div>
  </div>
  </div>




</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Header1 from '@/components/header1.vue'


export default {
  data (){
    return{
      categories: [],
      baseUrlApi: 'http://fundamentos.academlo.com/api/v1/'
    }
  },
  created(){
    this.getCategories()
  },
  methods: {
getCategories(){
  const url = 'http://fundamentos.academlo.com/api/v1/directories/5c82982e-b63e-4280-8287-4eba0e99716a/categories'

    axios.get(url)
      .then(response => {
        this.categories = response.data
        console.log(response)
        //alert(this.categories)
      })
      
    
}
  },
  name: 'home',
  components: {
    HelloWorld,
    Header1,
  }
}
</script>


