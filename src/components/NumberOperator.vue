<template>
    <input type="text" v-model="NumberOperator" v-on:input="sendInfo" class="input">
</template>

<script>
export default {
  name: 'NumberOperator',
  data() {
      return {
          NumberOperator:"+"
          }},
  methods: {
    sendInfo() {this.$emit('NumberOperator', this.NumberOperator)}
    }
}
</script>
<style scoped>
.input {
 width: 100px;
 height: 50px;
 font-size: 24px;
 text-align: center;
border-radius: 10px;
margin: 20px;
}
</style>