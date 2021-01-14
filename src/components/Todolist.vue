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
    <div class="container">
      <div class="row">
        <div class="col">
          <label>Todolist:</label>
        </div>
      </div>
      <div class="row">
        <div class="col-xl-12">
          <div class="todoitemBg">
            <ul class="listStyleNone">
              <TodoItem
                class="todoitem"
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
        </div>
      </div>
      <div class="row">
        <div class="col-xl-8">
          <div class="row">
            <div class="col-xl-3"></div>
            <div class="col-xl-6">
              <b-form-input
                id="input-large"
                size="lg"
                v-model="work"
                placeholder="Enter your name"
              ></b-form-input>
            </div>
            <div class="col-xl-3">
              <button
                class="btn-lg"
                size="lg"
                @click="handleSubmit"
                @keyup.enter="handleEnter"
              >
                HandleSubmit
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
h1.thisIsReallyAtest {
  color: red;
}
.col1 {
  background-color: yellowgreen;
}
.col2 {
  background-color: purple;
}
/* .todoitem {
  background-color: saddlebrown;
} */
.todoitemBg {
  background-color: skyblue;
}
.listStyleNone {
  list-style-type: none;
}
</style>
