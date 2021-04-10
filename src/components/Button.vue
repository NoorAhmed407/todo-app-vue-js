<template>
    <button class="btn" ref="btn" @mouseleave="hoverOut" @mouseenter="hover" @click="onClick">{{btnName}}</button>
</template>

<script>
export default {
  name: 'Button',
  props: ['btnName'],
  methods: {
      hover(){
          this.$refs['btn'].classList.replace('btn','hover');
      },
      hoverOut(){
          this.$refs['btn'].classList.replace('hover','btn');
      },
      onClick(){
          this.$emit('onClick');
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.btn {
    background-color: transparent;
    border: 2px solid black;
    padding: 10px;
    border-radius: 5px;
    font-weight: bold;
}

.hover{
    background-color: black;
    border: 2px solid black;
    border-radius: 5px;
    color: white;
    padding: 10px;
    font-weight: bold;
}

</style>
