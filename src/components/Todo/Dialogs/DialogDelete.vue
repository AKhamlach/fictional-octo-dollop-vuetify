<template>
  <v-dialog :value="true" persistent max-width="290">
    <v-card>
      <v-card-title class="headline"> Delete Task? </v-card-title>
      <v-card-text>Are you sure you want to delete task?</v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="green darken-1" text @click="$emit('close')"> No </v-btn>
        <v-btn
          color="red darken-1"
          text
          @click="$store.dispatch('deleteTask', task.id)"
        >
          True
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "DialogDelete",
  props: ["task"],
  methods: {
    delete(id) {
      this.$store.dispatch("deleteTask", id);
    },
  },
};
</script>

<style>
</style>

// "$store.dispatch('deleteTask', task.id)"