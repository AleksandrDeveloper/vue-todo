<template>
  <div>
    <slot></slot>
    <form @submit.prevent>
      <div class="form-group">
        <label for="title">Title</label>
        <input type="text" class="form-control" id="title" v-model="title" />
      </div>

      <div class="form-group">
        <label for="text">Text</label>
        <textarea class="form-control" id="text" v-model="text"></textarea>
      </div>

      <button type="submit" class="btn btn-primary" @click="addToDo">Submit</button>
    </form>
  </div>
</template>


<script>
export default {
  name: "Form",
  data() {
    return {
      title: "",
      text: "",
    };
  },
  methods: {
    addToDo() {
      const newToDo = {
        title: this.title,
        text: this.text,
        id: Math.random(),
      };
        this.text =''; 
        this.title = '';

        this.$emit('addToDoItem',newToDo)
    },
  },
};
</script>