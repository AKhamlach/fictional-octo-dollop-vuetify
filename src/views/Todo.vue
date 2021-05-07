<template>
  <div class="home">
    <field-add-task />

    <list-tasks v-if="$store.state.tasks.length" />
    <no-task v-else />
  </div>
</template>

<script>
import FieldAddTask from "../components/Todo/FieldAddTask.vue";
import ListTasks from "../components/Todo/ListTasks.vue";
import NoTask from "../components/Todo/NoTask.vue";

export default {
  name: "Todo",
  methods: {},
  data() {
    return {};
  },

  components: {
    "field-add-task": FieldAddTask,
    "list-tasks": ListTasks,
    "no-task": NoTask,
  },
};
</script>

<style lang="sass">
.no-tasks
  position: abolute
  left: 50%
  top: 50%
  transform: translate(50%,150%)
  opacity: 0.5
</style>
