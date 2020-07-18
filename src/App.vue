<template>
  <div>
    <h1>Hello!</h1>
    <TodoList></TodoList>
  </div>
</template>

<script>
//import component
import TodoList from "./components/TodoList";

//export component
export default {
  name: "App",
  //which components this component has
  components: {
    TodoList
  }
};
</script>

<style>
body {
  background-color: rgb(66, 66, 66);
  color: aliceblue;
}
</style>