<template>
  <div
    class="task-card rounded-md cursor-pointer flex items-center justify-between"
    @click="showDetails"
  >
    <h2 class="text-lg">{{ title }}</h2>
    <button class="delete-btn" @click.stop="deleteTask">Delete</button>
  </div>
</template>

<script>
export default {
  props: {
    title: String, // Todo object to display
    description: String,
    id: Number,
    status: String,
  },
  methods: {
    showDetails() {
      // Emit event to show details popup
      this.$emit("show-details", {
        title: this.title,
        description: this.description,
      });
    },
    deleteTask() {
      // Emit event to delete the task
      console.log("fukck you in task item");
      this.$emit("delete-task", {
        title: this.title,
        description: this.description,
        id: this.id,
        status: this.status,
      });
    },
  },
};
</script>

<style scoped>
.task-card {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}

.delete-btn {
  background-color: #f44336;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
  margin-left: 10px;
}
</style>
