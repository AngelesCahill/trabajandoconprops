<template>
  <div class="container text-center mt-5">
    <h1 v-text="mensaje"></h1>
    
    <table class="table mt-4" v-show="mostrando">
      <thead>
        <tr>
          <th>#</th>
          <th>Tarea</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(element,index) in listaTareas" :key="index">
          <td>{{listaTareas.id}}</td>
          <td>{{listaTareas.tarea}}</td>
        </tr>
      </tbody>
    </table>
    <hr>
    <Lista />
  </div>
</template>

<script>
import Lista from './mainHijo/Lista.vue'
export default {
  name: 'Main',
  data(){
    return {
        mostrando: true,
        mensaje: "Tareas agregadas: ",
        listaTareas: [
          {id: 1, tarea: 'Pagar Internet'},
          {id: 2, tarea: 'Ir al supermercado'},
          {id: 3, tarea: 'Comprar pan'},
          {id: 4, tarea: 'Pagar Netflix'},
          {id: 5, tarea: 'Comprar audifonos'},
          {id: 6, tarea: 'hacer Ejercicios'},
      ]
    }
  },
  methods: {
    mostrarTabla(){
      this.mostrando = !this.mostrando;
    }
  },
  components: {
    Lista
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
