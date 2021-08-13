<template>
<div class="m-4">
  <h3>Crea una nueva tarea</h3>

  <div class="input-control d-flex p-2 l-2">
    
    <label class="fs-4">Tarea  </label>
    <span class="fs-4">-</span>
    <input class="form-control r-5"
    type="text" 
    placeholder="Ingrese una nueva tarea"
    v-model="nuevaActividad">
    <button class="btn btn-primary" @click="agregarNuevaActividad">Crear</button>
  </div>
    <h3>Lista</h3>
    <ul class="list-group p-2">
      <li class="list-group-item" v-for="(actividades, $index) in actividades" 
      :key="$index">
      {{actividades}}

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
  display: inline;
  

};
#body {
  margin: 50px;
}
</style>
