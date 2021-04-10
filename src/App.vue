<template>
<div class="center">
  <div class="card">
  <h1>Todo App</h1>
    <div class="inputBox">
      <Input name="todo" :value="text" @input="changeText($event)"  />
      <Button btnName="Add Todo" @onClick="helloClick" />
    </div>
    <div v-if="todos.length > 0">
      <ul :v-for="item in todos">
          <li>{{item}}</li>
      </ul>
    </div>
  </div>
</div>

</template>

<script>
import Button from './components/Button.vue';
import Input from './components/input.vue';

export default {
  name: 'App',
  data(){
    return{
      text: '',
      todos: []
    }
  },
  components: {
    Button,
    Input
  },
  methods: {
    helloClick(){
     this.todos.push(this.text);
     this.text = "";
     console.log(this.todos);
    },
    changeText(event){
      this.text = event.target.value;
       console.log('Agaya',event.target.value);
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
</style>
