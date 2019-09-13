<template>
<div>



          <div class="home  flex-column d-flex " style="background: linear-gradient(0deg, rgba(195,34,93,1) 0%, rgba(101,45,253,1) 100%); height:300px;">
            <h1 class="p-2 bd-highlight" style="color:white">Excelsior!</h1>
            <br>
            <center>
            <a class="btn btn-primary btn-lg p-2 bd-highlight" href="/categories" role="button">Browse Categories</a>
            </center>
          </div>
        
 

<!-- div Container Features & Category-->
<div class="espacio">
          <h2>Featured</h2>

<div class="d-flex align-content-stretch flex-wrap container flex-row">

<card :product1="producto"></card>
<card :product1="producto"></card>
<card :product1="producto"></card>
</div>


<div class="card-deck col-12 pl-0 pr-0 divfeatures" id="featured-products">

</div>

      <!-- fin featured -->
 <br>  
 <br> 
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
    <div class="col-sm" v-for="categorie in categories8" :key="categorie.id">
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

 
</div>
</div>
</template>





<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Header1 from '@/components/header1.vue'
import ProductoDesc from '@/components/ProductoDesc.vue'
import Card from '@/components/card.vue'


export default {
  data (){
    return{
      categories: [],
      categories8: [],
      producto: {name: 'Patrocinado',
      description: 'El extranjero (en francés, LÉtranger) es la primera novela del escritor francés Albert Camus, publicada en 1942. El extranjero suele asociarse a la filosofía del absurdo y al existencialismo, aunque Camus siempre se distanció de esta última etiqueta. El protagonista, Meursault, es un francés argelino indiferente a la realidad por resultarle absurda e inabordable. El progreso tecnológico le ha privado de la participación en las decisiones colectivas y le ha convertido en "extranjero" dentro de lo que debería ser su propio entorno.',
      image: 'http://fundamentos.academlo.com/app/public/products/8-14-2-39-46-el-extranjero.jpg'},
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
        this.categories8 = this.categories.categories.slice(0, 8);
        //alert(this.categories)
        //alert(this.categories1)
        console.log(response)
        //alert('hola')
      })
      
    
}
  },
  name: 'home',
  components: {
  ProductoDesc,
  Card
  }
}
</script>