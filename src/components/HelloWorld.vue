<script>
export default {
  // put the component which used in template into name
  name: "HelloWorld",
  // 繼承parent component's property called mag, and its type is String
  props: {
    msg: String,
  },
};
</script>

<template>
  <!-- need a div to contain the context the include msg mustash -->
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
