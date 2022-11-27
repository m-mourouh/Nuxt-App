<template>
  <main>
    <h1 class="mb-5">Nuxt | Todo List</h1>
    <div class="create-new">
      <input
        type="text"
        v-model="newTask"
        placeholder="Add a new task"
        @keypress.enter="addTask"
        class="form-control"
      />
      <button @click="addTask" class="btn btn-dark ms-3">Add</button>
    </div>

    <div class="tasks">
      <Task v-for="(task, i) in $store.state.tasks" :key="i" :task="task" />
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
    };
  },
  methods: {
    addTask() {
      if (this.newTask.trim()) {
        this.$store.commit("ADD_TASK", this.newTask);
        this.newTask = "";
      }
    },
  },
};
</script>


