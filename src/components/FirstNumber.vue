<template>
    <input type="text" v-model="FirstNumber" v-on:input="sendInfo" class="input">
</template>

<script>

export default {
  name: 'FirstNumber',
   data() {
      return {
          FirstNumber: 0
          }}, 
  methods: {
    sendInfo () {this.$emit('FirstNumber', this.FirstNumber)}
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