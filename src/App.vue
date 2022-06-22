<template>
  <div id="app">
    <h2>{{titulo1}}</h2>
    <h3>Tarea: <span><input type="text" v-model="name"> <button @click="crearTarea">Crear</button></span></h3>
    <br>
    <h2>{{titulo2}}</h2>
    <div class="lista">
      <ul>
        <li v-for="(tarea, index) in tareas" :key="index">
          {{index}}. {{tarea.tarea}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      titulo1: "Crea una nueva tarea",
      titulo2: "Lista",
      name: "",
      tareas: [
        {"tarea" : "Ir al supermercado"},
        {"tarea" : "Pagar internet"},
        {"tarea" : "Renovar suscripción de Netflix"}
      ]
    }
  },
  methods: {
    crearTarea() {
      this.tareas.push({"tarea" : this.name});
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}

h2 {
  color: gray;
}
.lista {
  text-align: left;
  display: inline-block;
}
</style>
