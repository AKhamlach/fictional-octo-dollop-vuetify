<template>
  <div>
    <v-list-item
      @click="$store.commit('doneTask', task.id)"
      :class="{ 'blue lighten-4': task.done }"
    >
      <template v-slot:default>
        <v-list-item-action>
          <v-checkbox :input-value="task.done" color="primary"></v-checkbox>
        </v-list-item-action>

        <v-list-item-content>
          <v-list-item-title
            :class="{ 'text-decoration-line-through': task.done }"
            >{{ task.title }}</v-list-item-title
          >
        </v-list-item-content>

        <v-list-item-action v-if="task.dueDate">
          <v-list-item-action-text>
            <v-icon small>mdi-calendar </v-icon>
            {{ task.dueDate | niceDate }}
          </v-list-item-action-text>
        </v-list-item-action>

        <v-list-item-action>
          <task-menu :task="task" />
        </v-list-item-action>
      </template>
    </v-list-item>

    <v-divider></v-divider>
  </div>
</template>

<script>
import { format } from "date-fns";
import TaskMenu from "./TaskMenu.vue";

export default {
  name: "Task",
  props: ["task"],
  filters: {
    niceDate(value) {
      return format(new Date(value), "dd MMM yyyy");
    },
  },
  components: { "task-menu": TaskMenu },
};
</script>

<style>
</style>