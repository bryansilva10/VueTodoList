<template>
  <h1>Hello fro Todo List Template</h1>
</template>

<script>
export default {
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