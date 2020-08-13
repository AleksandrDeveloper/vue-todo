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
        {{item.title}} <span>{{item.text}} </span> <button @click="delite(item.id)" class="btn btn-danger">Delite</button>
      </li>
    </ul>
  </div>
</template> 

<script>


export default {
  name: 'App',
  data() {
    return {
      todoArr:[
        {
          title:'Hello 1111',
          text:'Lorem ipsum dolor sit.',
          id:Math.random()*100
        },
        {
          title:'Hello 2222',
          text:'Lorem ipsum dolor sit.',
          id:Math.random()*100
        },
        {
          title:'Hello 3333',
          text:'Lorem ipsum dolor sit.',
          id:Math.random()*100
        },
      ]
    }
  },
  components: {
  },
  methods:{
    delite(id){
      this.todoArr = [...this.todoArr].filter(item=>item.id !== id)
    }
  }
}
</script>

<style>

</style>
