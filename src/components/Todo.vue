<template>
  <li class="d-flex align-items-center list-group-item">
    <button class="btn border-0 text-left flex-grow-1">{{todoString}}</button>
    <form class="flex-grow-1">
      <input type="text" class="form-control" />
    </form>
    <button class="btn btn-outline-primary">Edit</button>
    <button class="btn btn-outline-danger">Delete</button>
  </li>
</template>

<script>
export default {
  //accepts props
  props: {
    todoString: String,
    completed: Boolean
  },
  //data for this component
  data() {
    return {
      isEditing: false,
      newTodoString: ""
    };
  }
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>