<template>

<input :name="name" :value="value" class="inpt" placeholder="Write Todo"/>

</template>

<script>
export default {
  name: 'Input',
  props: ['name','value'],
  methods: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.inpt {
   height:  30px;
   margin: 10px;
   background-color: transparent;
   border: 2px solid black;
   /* border-bottom: 1px solid black; */
   border-radius: 5px;
   text-align: center;
}




</style>
