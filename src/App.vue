<template>
  <div id="app">
    <h1 class="my-5">{{ titulo }}</h1>
    <span>{{ texto }}</span>
    <input
      type="text"
      placeholder="Ingresa nueva tarea"
      v-model="nuevaTarea"
      class="mx-2"
    />
    <button v-on:click="crearTarea">Crear</button>
    <h2 class="my-5">{{ subtitulo }}</h2>
    <div class="list">
      <ul>
        <li v-for="(tarea, i) in tareas" :key="i">
          {{ i }} - {{ tarea.item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      titulo: "Crea una nueva tarea",
      subtitulo: "Lista",
      texto: "Tarea",
      tareas: [
        {
          item: "Ir al supermercado",
        },
        {
          item: "Pagar Internet",
        },
        {
          item: "Pagar Netflix",
        },
      ],
      nuevaTarea: "",
    };
  },
  methods: {
    crearTarea() {
      this.tareas.push({
        item: this.nuevaTarea,
      });
      this.nuevaTarea = "";
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.list {
  text-align: left;
  width: 200px;
  margin: auto;
}
</style>
