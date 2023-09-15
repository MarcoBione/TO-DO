<template>
  <div class="py-5 border-b-2 border-w flex justify-center">
    <!-- imput -->
    <input
      type="text"
      name="task-to-do"
      id="task-to-do"
      class="_myinput"
      placeholder="Write to do"
      v-model="task.name"
      @keyup.enter="addTask()"
    />
    <input type="text" id="notes" placeholder="Add a task note?" class="_myinput" v-model="task.note" @keyup.enter="addTask()">
    <button class="_mybtn px-3 border-2-w" @click="addTask()">Add</button>
  </div>
  <div>
    <TaskListComponent :taskList="tasks" @delete-task="deleteTask" />
  </div>
</template>

<script lang="ts">

import TaskListComponent from "./TaskListComponent.vue";
import type { Task } from "./interfaces";

interface InitialState {
  task: Task;
  tasks: Task[];
}

const initialState: InitialState = {
  task: {
    id: 0,
    name: "",
    note: "",
    date: "",
    status: false,
  },
  tasks: [], // Un array vuoto di oggetti Task
};


export default {
  components: { TaskListComponent },
  data(): InitialState {
    return initialState;
  },

  methods: {
  addTask() {
    if (this.task.name == "") {
      console.log("vuoto");
    } else {
      const newTask = { ...this.task };
      newTask.id++;
      this.tasks.push(newTask);
      this.task.name = "";
      this.task.note = "";
      //console.log(this.tasks);
    }
  },
  deleteTask(id:number){
    const indexToDelete = this.tasks.findIndex((task) => task.id === id);
    if (indexToDelete >= 0) {
        this.tasks.splice(indexToDelete, 1);
      }else{
        console.log('error');
      }
  }
},

};
</script>

<style scoped>
._myinput {
  padding: 5px;
  border: 1px solid black;
  border-radius: 5px;
}

._myinput {
  background-color: #74546a;
  color: white;
}
</style>