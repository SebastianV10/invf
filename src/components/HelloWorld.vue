<template>
  <div class="container">
    <div class="row">
        <div class="col-md7">
            <table class="table-responsive ">
              <thead>
                <tr>
                    <th>Nombre</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="edificio in edificios" :key="edificio.id" >
                  <td v-text="edificio.nombre"> 
                  </td>
                  <td>
                    <a href="" class="btn btn-warning">ver salones</a>
                    <a href="" class="btn btn-warning">Editar</a>
                    <form action="" method="POST" class="d-inline">
                      <button type="submit" class="btn btn-danger">Eliminar</button>
                    </form>
                  </td>

                </tr>    
                
              </tbody>
            </table>
        </div>
        <!--Formulario de Creación Edificio-->
        <div class="col-md5" style="float: right; position: fixed; right:40px;">
            <h3 class="test-center mb-4">Agregar Edificio</h3>
            
              <div class="form-group">
                <input type="text" name="nombre" value="" class="form-control" placeholder="nombre" v-model="nombreedificio">
              </div>
              <button @click="crearedificio" class="btn btn-success">Guardar</button>
            
        </div>
  </div>
</div>
</template>

<script>
import axios from 'axios'
import VueCsrf from 'vue-csrf'
export default {
  VueCsrf, 
  name: 'HelloWorld',
  data: () => ({
    edificios: [],
    nombreedificio: ''
  }),
  mounted() {
    this.llamaredificio()
    console.log(this.$csrfToken)
  },
  methods: {
    llamaredificio: function () {
      var that = this;
      axios.get('http://localhost:8080/inventarioBack/public/api/edificio')
      .then(function(response){
        that.edificios = [...response.data].slice(0, 10)
          console.log()
      })
    },
    crearedificio: function(){
      axios.post('http://localhost:8080/inventarioBack/public/api/agregarEdificio', {nombre: this.nombreedificio}, {headers: {'X-CSRF-TOKEN': this.$csrfToken}})
      .then(function(response){
        console.log(response)
        this.llamaredificio()
      })
    }
  }
}
</script>


<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
