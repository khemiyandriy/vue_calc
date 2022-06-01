<template>
<div id="app">
  <FirstNumber v-on:FirstNumber="First"/>
  <NumberOperator v-on:NumberOperator="theOperator"/>
  <FirstNumber v-on:FirstNumber="Second"/>
  <p class="text">Result: {{result}}</p>
</div>
</template>

<script>
import FirstNumber from '@/components/FirstNumber.vue'
import NumberOperator from '@/components/NumberOperator.vue' 

export default {
  name: 'App',
    data() {
    return {
      FirstNumber: 0,
      SecondNumber: 0,
      NumberOperator:'+'
    }
  },   
  methods: {
    First(FirstNumber){this.FirstNumber = FirstNumber},
    theOperator(NumberOperator){this.NumberOperator = NumberOperator},
    Second(SecondNumber){this.SecondNumber = SecondNumber},
  },
  computed: {
    result() {
      console.log(this.FirstNumber, this.SecondNumber, this.NumberOperator)
      if (this.NumberOperator==="-"){return eval(+this.FirstNumber - +this.SecondNumber)} else
      if (this.NumberOperator==="*"){return eval(+this.FirstNumber * +this.SecondNumber)} else 
      if (this.NumberOperator==="/"){return eval(+this.FirstNumber / +this.SecondNumber)} else
      if (this.NumberOperator==="+"){return eval(+this.FirstNumber + +this.SecondNumber)} else
       return "Operator Error"; 
    }
  },
  components: {FirstNumber, NumberOperator}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 24px;
  height: 200px;
  width: 500px;
  background: linear-gradient(45deg, rgba(105,255,215,1) 0%, rgba(0,128,128,1) 100%);
  margin: 0;
  padding: 0;
}
.text{
  color: azure;
}
</style>
