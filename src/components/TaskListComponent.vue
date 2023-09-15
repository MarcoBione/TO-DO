<template>
  <!-- tasklist -->
  <div class="py-5">
    <!-- title -->
    <section class="text-center">
      <h2 class="color-w uppercase">Task List</h2>
    </section>
    <!-- Tasklist -->
    <section
      class="flex justify-between align-middle"
      v-for="task in taskList"
      :key="task.id"
    >
      <!-- taskname -->
      <h4 class="uppercase align-middle">{{ task.name }}</h4>
      <p class="uppercase align-middle">Notes: {{ task.note }}</p>
      <!-- buttons -->
      <div>
        <button
          class="_mybtn border-2 border-yellow-500 p-2"
          @click="updateTask(task.id)"
        >
          Edit
        </button>
        <button
          class="_mybtn border-2 border-red-500 p-2"
          @click="deleteTask(task.id)"
        >
          Delete
        </button>
      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent, defineEmits } from "vue";
import type { Task } from "./interfaces";

export default defineComponent({
  name: "TaskListComponent",
  props: ["taskList"],

  data() {
    return {};
  },
  methods: {
    updateTask(id:number) {

    },

    deleteTask(id: number) {
      // Emit the custom event to notify the parent component
      this.$emit("delete-task", id);
    },
  },
});
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
