<template>
  <div class="container pt-5">
    <form>
      <div class="form-group">
        <label for="title">Title</label>
        <input type="email" class="form-control" id="title" />
      </div>

      <div class="form-group">
        <label for="text">Text</label>
        <textarea class="form-control" id="text"></textarea>
      </div>

      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
    <hr />

    <ul class="list-group">
      <li class="list-group-item" v-for="item in todoArr" :key="item.id">

      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ToDoItem",
  props: {
    title: String,
    text: String,
    id: Number,
  },
};
</script>

<style scope>
textarea {
  width: 100%;
  height: 200px;
}
</style>

