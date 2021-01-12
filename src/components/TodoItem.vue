<script>
// import { component } from "vue/types/umd";
// generate automately, that cause 98% after emitting CopyPlugin
export default {
  name: "todoitem",
  props: ["content", "index"],
  methods: {
    handleDelete() {
      console.log("handleDelete");
      this.$emit("delete", this.index);
      // send index value to parent component
    },
  },
};
</script>

<template>
  <div>
    <!-- <h2>TodoItem is me!!!!!</h2> -->
    <li @click="handleDelete">{{ content }}</li>
  </div>
</template>

<style>
</style>