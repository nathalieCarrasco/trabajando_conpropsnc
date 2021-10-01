/*En el componente padre (App.vue) debes crear la estructura del formulario en                       
conjunto con el botón y pasar los datos al componente hijo medianteprops,aligual                             
que recibir como evento la información enviada desde el hijo para eliminar un dato                           
de las teras (arreglo)  */

<template>
<div id="app">
    <h2> Mis Notas y Apuntes Con Vue </h2>
    <label for="tarea" >Tarea</label>
    <input type="text" v-model="nuevaTarea" placeholder="Ingresa nueva tarea">
    <button @click="agregarTarea">Crear</button>
        <h4>Lista</h4>
        <ul >
        <ListadoTareas v-for="(tarea,index) in tareas" :key="index" :tareaNueva="tarea" v-on:eliminarTarea="tareas.splice(index,1)" ></ListadoTareas>
        </ul>  
</div>
</template>

<script>
import ListadoTareas from '@/components/ListadoTareas.vue';

export default {
  name: 'App',
  components: {
    ListadoTareas
  },
    data: () => ({
    nuevaTarea : '',
    tareas:[]
  }),
  methods: {
    agregarTarea() {
      this.tareas.push( this.nuevaTarea )
      this.nuevaTarea = ''
    },
  }
};
</script>

<style>

*{
  background-size: cover;
  background-image: url(https://image.freepik.com/foto-gratis/lapiz-rayado-rojo-sobre-fondo-papel-rayado-cuaderno-blanco-blanco-espacio-copia-regreso-escuela-educacion-concepto-aprendizaje_206881-113.jpg);
}
h2{
margin-left: 500px;
font-family: 'Lucida Sans', sans-serif;
font-size: 35px;

}
h4{
  margin-left: 600px;
  font-family:'Lucida Sans', sans-serif ;
  font-size: 24px;
}
label{
margin-left: 550px;
}

  ul {
    width: 20%;
    margin-left: 550px;
    }
</style>
