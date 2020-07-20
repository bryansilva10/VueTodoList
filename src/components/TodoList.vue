<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <p class="display-3">Vue Todo List</p>
      </div>
    </div>
    <div class="row">
      <NewTodo @on-addtodo="addTodo($event)" />
    </div>
    <div class="row">
      <div class="col-12 col-lg-6">
        <ul class="list-group">
          <Todo
            v-for="(todo, index) in todos"
            :key="index"
            :todoString="todo.todoString"
            :completed="todo.completed"
            @on-delete="deleteTodo(todo)"
            @on-toggle="toggleTodo(todo)"
            @on-edit="editTodo(todo, $event)"
          />
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
//import components
import Todo from "./Todo";
import NewTodo from "./NewTodo";
export default {
  //register components
  components: {
    Todo,
    NewTodo
  },
  //data or state for the component
  data() {
    return {
      todos: [
        { todoString: "Buy Car", completed: false },
        { todoString: "Buy Milk", completed: true },
        { todoString: "Buy Chocolate", completed: false },
        { todoString: "Buy Clothes", completed: true }
      ]
    };
  },
  //methods for component
  methods: {
    //method to add an item
    addTodo(newTodo) {
      //push new todo to data
      this.todos.push({
        todoString: newTodo,
        completed: false
      });
    },

    //method to toggle between completed and uncompleted
    toggleTodo(todo) {
      //change current boolean state
      todo.completed = !todo.completed;
    },

    //method to edit todo item
    editTodo(todo, newTodoString) {
      //update string with new data
      todo.todoString = newTodoString;
    },

    //delete item
    deleteTodo(deleteTodo) {
      //update array filtering those items that are not marked to be deleted
      this.todos = this.todos.filter(
        todo => todo.todoString !== deleteTodo.todoString
      );
    }
  }
};
</script>

<style>
</style>