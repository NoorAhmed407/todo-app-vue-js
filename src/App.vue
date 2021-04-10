<template>
<div>

<Input name="Todo" :value="text" @input=changeText($event) />
<Button @onClick="helloClick" />
</div>

</template>

<script>
import Button from './components/Button.vue';
import Input from './components/input.vue';

export default {
  name: 'App',
  data(){
    return{
      text: ''
    }
  },
  components: {
    Button,
    Input
  },
  methods: {
    helloClick(){
      console.log('Text',this.text);
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
  /* margin-top: 60px; */
}
</style>
