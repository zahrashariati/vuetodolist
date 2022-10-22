
<template>
    
  

  <customHeader></customHeader>
  <main>
    <section class="jumbotron grey">
      <div class="container d-flex flex-column align-items-center">
        <h1 class="jumbotron-heading">Welcome</h1>
        <p class="lead text-muted">To get started, add some items to your list:</p>
        <FormAddTodo @add-todo="addTodo"></FormAddTodo>
      </div>
    </section>
    
    <div class="todolist">
      <div class="container">
        <div class="de-flex flex-colun align-items-center">
          <TodoList :todos="todos" @delete-todo="deleteToDo" @edit-todo="editTodo"></TodoList>
        </div>
      </div>
    </div>
  </main>
  
    
    
</template>




<script >


import Header from './components/Header.vue'
import TodoList from './components/Todo-list.vue';
import FormAddTodo from './components/FormAddTodo.vue';

 export default{

  components:{
    "customHeader": Header,
    TodoList,
    FormAddTodo
  },
  data(){
    return{
      todos:[
        
      ]
    }
  },
  methods:{
    addTodo(text){
      this.todos.push({
        key: Date.now(),
        done: false,
        text
      });
    },
    deleteToDo(key){
      
      this.todos = this.todos.filter(item => item.key != key)
      console.log(key)
    },

    editTodo({key , text}){
      this.todos = this.todos.map(item =>{
        if(item.key == key){
          return{
            ...item,
            text : text,
          }
        }
        return item;
      })

    }
  }

}

</script>




<style>

.grey{
  background-color: #c0c0c0;
}

</style>
