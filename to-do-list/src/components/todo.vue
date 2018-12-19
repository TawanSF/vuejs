<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" @keyup.enter="addNewTodo()" v-model="newTodoText">
    <ul>
      <li is="todo-item"
      v-for="(todo, index) in todos"
      :key="todo.id"
      :title="todo.title"
      v-on:remove="todos.splice(index, 1)"
      >
      </li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './todo-item.vue';
export default {
  data() {
    return {
      msg: 'to-do list',
      newTodoText: '',
      todos: [],
      nextTodoId: 1,
    };
  },
  components: { TodoItem },
  methods: {
    addNewTodo () {
      this.todos.push({
        id: this.nextTodoId++,
        title: this.newTodoText,
      });
      this.newTodoText = '';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
