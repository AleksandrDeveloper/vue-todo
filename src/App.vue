<template>
  <div class="container pt-5">
    <form-component
    @addToDoItem="addToDo($event)"
    >
      <h1>ToDo list app</h1>
    </form-component>
    
    <hr />

    <ul class="list-group">
      <to-do-item 
      v-for="item in todoArr" :key="item.id"
      :title='item.title'
      :text='item.text'
      :id="item.id"
      :delite='delite'  
      > 
      </to-do-item>
    </ul>
  </div>
</template> 

<script>
import ToDoItem from './components/ToDoItem';
import FormComponent from './components/Form'

export default {
  name: 'App',
  data() {
    return {
      title:'',
      text:'',
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

      ]
    }
  },
  components: {
    ToDoItem,
    FormComponent,
  },
  methods:{
    delite(id){
      this.todoArr = [...this.todoArr].filter(item=>item.id !== id)
    },
    addToDo(obj){
      
      // const newToDo = {
      //   title:this.title,
      //   text:this.text,
      //   id:Math.random()
      // }

      // this.text ='' 
      // this.title = ''

      this.todoArr = [...this.todoArr,obj]
    }
  }
}
</script>

<style>

</style>
