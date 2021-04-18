<template>
<div class="center">
  <div class="card">
  <h1>Todo App</h1>
    <div class="inputBox">
      <Input name="todo" :value="text" @input="changeText($event)"  />
      <Button btnName="Add Todo" @onClick="addTodo" />
    </div>
    <div v-if="todos.length > 0">
          <div class="todostrip" v-for="(todo, index) in todos" :key=index>
            <div><h2>{{todo}}</h2></div>
            <div><Button btnName="Delete" @onClick="deleteTodo(todo)" /></div>
          </div>
      </div>
  </div>
</div>

</template>

<script>
import Button from './components/Button.vue';
import Input from './components/input.vue';

export default {
  name: 'App',
  data() {
    return{
      text: '',
      todos: []
    };
  },
  components: {
    Button,
    Input
  },
  
  methods: {
    addTodo(){
      console.log('Todos',this.todos);
      this.todos.push(this.text);
      console.log(JSON.parse(JSON.stringify(this.todos)));
      this.text = "";
    },
    changeText(event){
      this.text = event.target.value;
       console.log('Agaya',event.target.value);
    },
    deleteTodo(item){
      console.log('Item', item);
      this.todos = this.todos.filter((val,ind)=> val !== item);
      console.log('After Delete', JSON.parse(JSON.stringify(this.todos)));
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
}

.center {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.card{
   background-color:  #ff91f8 ;
   border-radius: 10px;
   padding: 20px;
}
.inputBox{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.todostrip{
  display: flex;
  flex-direction: row;
  background-color: #fff;
  padding: 10px;
  border-radius: 10px;
  justify-content: space-between;
  align-items: center;
  margin: 5px 0px;
}

</style>
