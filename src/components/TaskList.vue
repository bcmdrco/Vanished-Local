<template>
  <div class="task-list">
    <section class="task-items">
      <TaskItem
        v-for="(task, id) in tasks"
        :key="id"
        :task="task"
      />
    </section>
  </div>
</template>

<script>
import TaskItem from "@/components/TaskItem.vue";

export default {
  name: "TaskList",
  components: {
    TaskItem
  },
  computed: {
    tasks() {
      return this.$store.state.tasks.slice();
    }
  }
};
</script>

<style scoped>
section {
  margin: 20px 0;
}

.task-items {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
