<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: { TodoItem },
  name: "Todolist",
  component: {},
  props: {
    msg: String,
  },
  data() {
    return {
      work: "",
      items: [],
      // [{ fruit: "orange" }, { fruit: "watermelon" }],
    };
  },
  methods: {
    alertMsg() {
      console.log("alertMsg");
    },

    handleSubmit() {
      console.log("handleSubmit");
      this.items.push(this.work);
      this.work = "";
      console.log();
    },
    handleDelete(index) {
      this.items.splice(index, 1);
    },
  },
};

// console.log(this);  => undefined
</script>

<template>
  <div>
    <h1 class="thisIsReallyAtest">This is a test..........</h1>
    <p>{{ msg }}</p>
    <button @click="alertMsg">Alert</button>
    <input v-model="work" />
    <button @click="handleSubmit">HandleSubmit</button>
    <ul>
      <TodoItem
        v-for="(item, index) in items"
        :key="item.fruit"
        :content="item"
        :index="index"
        @delete="handleDelete"
      >
        {{ item }}
      </TodoItem>
    </ul>
  </div>
</template>

<style scope>
h1.thisIsReallyAtest {
  color: red;
}
</style>