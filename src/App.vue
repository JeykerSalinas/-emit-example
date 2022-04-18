<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h1>Todo List App</h1>
        </div>
      </div>
      <div class="row">
        <h2 class="col-12">Tarea</h2>
        <div class="input-group mb-3">
          <input
            type="text"
            class="form-control"
            placeholder=""
            aria-label="Example text with button addon"
            aria-describedby="button-addon1"
            v-model="myTask"
          />
          <button
            class="btn btn-outline-secondary"
            type="button"
            id="button-addon1"
            @click="addTask"
          >
            Crear
          </button>
        </div>
        <TaskList :items="items" @click="removeTask" />
      </div>
    </div>
  </div>
</template>

<script>
import TaskList from "./components/TaskList.vue";
export default {
  name: "App",
  data() {
    return {
      myTask: "",
      items: [],
    };
  },
  methods: {
    addTask() {
      this.myTask === ""
        ? alert("Por favor ingresar tarea")
        : this.items.push(this.myTask) && (this.myTask = "");
    },
    removeTask(index) {
      console.log(index);
      this.items.splice(index, 1);
    },
  },
  components: {
    TaskList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
