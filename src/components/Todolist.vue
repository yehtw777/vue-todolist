<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: {
    TodoItem,
  },
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
    },

    handleDelete(index) {
      this.items.splice(index, 1);
    },

    // handleEnter() {

    //   this.items.push(this.work);
    //   this.work = "";
    // },

    // mounted() {
    //   window.addEventListener('keyup', function (e) {
    //       if (e.keyCode === 108) {
    //         console.log("handleEnter");
    //       }
    //     }
    //   }
  },
};

// console.log(this);  => undefined
</script>

<template>
  <div>
    <h1 class="thisIsReallyAtest">This is a test..........</h1>
    <p>{{ msg }}</p>
    <button @click="alertMsg">Alert</button>
    <b-container fluid>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-large">Todolist:</label>
        </b-col>
        <b-col sm="10">
          <b-form-input
            id="input-large"
            size="lg"
            v-model="work"
            placeholder="Enter your name"
          ></b-form-input>
        </b-col>
      </b-row>
    </b-container>
    <button @click="handleSubmit" @keyup.enter="handleEnter">
      HandleSubmit
    </button>
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

<style>
h1.thisIsReallyAtest {
  color: red;
}
</style>
