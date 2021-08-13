<template>
<div>
  <h1>Crea una nueva tarea</h1>

  <div class="input-control">
    <label for="">Tarea</label>
    <input 
    type="text" 
    placeholder="Ingrese una nueva tarea"
    v-model="nuevaActividad">
    <button @click="agregarNuevaActividad">Crear</button>
  </div>
    <h1>Lista</h1>
    <ul>
      <li v-for="(actividades, $index) in actividades" 
      :key="$index">
      {{actividad}}

      </li> 
    </ul>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    nuevaActividad: "",
    actividades: ["pagar el netflix", "ir al super"],
  }),
  methods: {
    agregarNuevaActividad() {
      this.actividades.push(this.nuevaActividad)
      this.nuevaActividad = "";
    },
  },
};


</script>

<style scoped>
input-control {

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
