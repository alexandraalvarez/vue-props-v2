<template>
  <div id="app">
    <h1>Lista de tareas con Props</h1>
    <form>
      <label for="">Tareas</label>
      <input v-model="task" placeholder="Agrega una tarea">
      <button class="btn" @click.prevent="add_task">Agregar</button>
    </form>
    <ul id="task-ul">
      <li v-for="task in tasks" :key="task">
        {{task}}
        <button class="btn btn-delete" @click.prevent="delete_task">Eliminar tarea</button>
      </li>
    </ul>
  </div>
</template>

<script>

  export default {
    name: 'app-component',
    //props:{},
    data: function() {
      return {
        tasks:[],
        task:"",
      };
    },
    //computed:{},
    //components:{},
    methods:{
      add_task () { 
        alert(this.task)
        this.tasks.push(this.task)
        this.task="";
      },
      delete_task () {
        this.tasks.pop(this.task)
      }
    }  
  }
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #6AF7E0;
  border: #000000 solid 3px;
  width: 50%;
  margin: 10% auto;
}

#task-ul {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

#task-ul li {
  display: flex;
  justify-content: center;
  color: #000000;
}

label {
  margin-right: 1rem;
}

.btn {
  color: #000000;
  background-color: #F7E6A2 ;
  border-color: #AE9324;
}

.btn-delete {
  margin-left: 1rem;
}

.btn:hover {
  background-color:#AE9324;
  color: #FFFFFF;
}

</style>
