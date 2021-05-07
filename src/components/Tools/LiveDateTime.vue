<template>
  <div class="ml-3 text-subtitle-1">{{ date }}</div>
</template>

<script>
import { format } from "date-fns";

export default {
  name: "LiveDateTime",
  data() {
    return {
      date: "",
    };
  },
  methods: {
    getDate() {
      this.date = format(new Date(), "dd MMMM, H:mm:ss");
      setTimeout(this.getDate, 1000);
    },
  },
  mounted() {
    this.getDate();
  },
};
</script>

<style>
</style>