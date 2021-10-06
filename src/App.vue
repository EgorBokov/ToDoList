<template>
  <div id="app">
  <div class="all">
  <Search @addTask="addTask" :todos="todos" />
  <div class="container">
   <List @changeStatus="changeStatus" @deleteTask="deleteTask" :todos="todos" />
   </div>
   <div class="butts">
   <Buttons @saveList="saveList" @clearList="clearList" />
   </div>
   </div>
  </div>
</template>



<script>
import List from './components/List'
import Search from './components/Search'
import Buttons from './components/Buttons'

export default {
  name: 'App',
  components: {
    List ,
    Search,
    Buttons,
  },
  methods: {
    changeStatus(id) {
        for (const todo of this.todos) {
          if (todo.id === id) {
            todo.isDone = !todo.isDone
          }
        }
        },
        clearList(){
          this.todos = [];
          localStorage.clear();
        },
        saveList(){
          let todoList = JSON.stringify(this.todos);
            localStorage.setItem("todoList", todoList);


            console.log(JSON.parse(localStorage.getItem("todoList")));
        },
        addTask(inputValue){
            if (inputValue != '') {
              if (this.todos[this.todos.length -1]) {
                this.todos.push({title: inputValue, isDone: false, id: this.todos[this.todos.length -1].id + 1});
              } else {
                this.todos.push({title: inputValue, isDone: false, id: 0});
              }
              this.inputValue = '';
          }
        },
     deleteTask(id) {
          for (let i = 0; i < this.todos.length; i++) {
            if (this.todos[i].id === id) {
              this.todos.splice(i, 1);
            }
          }
        }
    },
  data() {
    return {
      todos: [
      
      ]
    }
  },
  mounted(){
if ( localStorage.getItem("todoList") != null ) {
          let jsonTodos = JSON.parse(localStorage.getItem("todoList"));
        for ( let i = 0; i < jsonTodos.length; i++ ) {
          this.todos.push(jsonTodos[i]);}        
  }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.title {
  color: yellow
}

li {
  list-style: none;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.all {
  padding-top: 20px;
  width: 579px;
  border: 1px solid black;
  background-color: #CDAF95;
}
</style>

<style>
*{
font-family: 'Arial';
}

.container { 
  margin-top: 10px;
  overflow: scroll;
  height: 555px;
  width: auto;
}

</style>
