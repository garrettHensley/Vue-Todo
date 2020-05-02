<template>
  <div class="main">
    <div class="container flexcol">
      <h1>Todo List</h1>
      <input type="text" v-model="text" />
      <button @click="addTo()">Add</button>
      <div v-for="(item, index) in list" :key="item.id" class="flexme">
        <Todo class="" :text="item" />
        <button @click="remove(index)">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
import Todo from "@/components/Todo.vue";

export default {
  name: "HelloWorld",
  data() {
    return {
      text: null,
      list: [],
    };
  },
  components: {
    Todo,
  },
  props: {
    msg: String,
  },
  methods: {
    addTo() {
      this.list.push(this.text);
    },
    remove(index) {
      this.list.splice(index, 1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
h1 {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 100;
}
.main {
  display: flex;
  justify-content: center;
}
.flexme {
  display: inline-flex;
}
.flexcol {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.container {
  background-color: #aa9d8f;
  color: #f7f8f7;
  border-radius: 0.5em;
  padding: 1em;
  width: 20em;
}
</style>
