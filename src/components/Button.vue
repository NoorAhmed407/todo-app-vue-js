<template>
    <button class="btn" ref="btn" @mouseleave="hoverOut" @mouseenter="hover" @click="onClick">Hello</button>
</template>

<script>
export default {
  name: 'Button',
  props: [],
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
    padding: 5px;
    border-radius: 5px;
    width: 10vw;
}

.hover{
    background-color: black;
    border: 2px solid black;
    border-radius: 5px;
    color: white;
    padding: 5px;
    width: 10vw;
}

</style>
