<template>

    <input :name="name" v-model="value" />

</template>

<script>
export default {
  name: 'Input',
  props: ['name', 'value',],
  methods: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.inpt {
   height:  30px;
   margin: 10px;
   border: 1px solid black;
   border-radius: 5px;
   text-align: center;
}




</style>
