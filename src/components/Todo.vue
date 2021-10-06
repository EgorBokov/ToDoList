<template>
<div class="main">
  <li class="hello">
    <div class="task_text">
      <p :class="{'isDone': todo.isDone}">{{todo.title}}</p>
    </div>
    <div class="task_buttons">
        <button class="done_btn" @click="$emit('changeStatus', todo.id)">✔</button>
        <button @click="$emit('deleteTask', todo.id)">✖</button>
    </div>
  </li>
</div>
</template>


<script>


export default {
  name: 'Todo',
  props: ['todo','todos']
}
</script>

<style>
.isDone {
    color: green;
    text-decoration: line-through;
}

</style>

<style scoped>
.main {
  background-color:#FFFAFA;
  width: 500px;
  padding: 0;
  margin: 0;
  margin-top:15px;
  padding-inline-start: 0;
  border-radius: 7px;
  transition: 0.2s ease;
}

p {
  max-width: 100%;
  word-wrap: break-word;
  padding-left: 15px;
}

button {
  border: none;
  background-color: 	#A52A2A;
  border-radius:2px;
  color: white;
  border: 1px solid transparent;
  transition: all 0.2s ease;
  text-align:center;
  padding:2px 5px;
  box-sizing: border-box;
  width: 25px;
  height: 25px;
}

.done_btn {
  background-color: #008000;
  margin-right: 2px;
}

.done_btn:hover {
  border: 2px solid #008000;
  color: #008000;
}

button:hover {
  background-color: transparent;
  border: 2px solid 	#A52A2A;
  color: 	#A52A2A;
}


.main:hover{
  box-shadow:4px 4px 10px rgba(255,255,255,0.56);
}

input {
  height: 25px;
  width: 25px;
}

li {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding-inline-start: 0;
}

ul {
   padding-inline-start: 0;
}

.task_buttons{
  
  display: flex;
   flex-direction: row;
   align-items: center;
   margin: 15px;
}
.task_text{
  width: 400px;
  text-align: left;
}

</style>