<template>
   <li class="list-group-item">
      {{title}} 
      <span>
        <strong>{{text}}</strong> 
      </span> 
      <br>
      <button 
      @click="delite(id)" 
      class="btn btn-danger">
        Delite
      </button>
   </li>
</template>

<script>
export default {
  name: "ToDoItem",
  props: {
    title: String,
    text: String,
    id: Number,
    delite:Function
  },
};
</script>

<style scope>
textarea {
  width: 100%;
  height: 200px;
}
</style> 

