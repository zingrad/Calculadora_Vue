<script setup>
    import {reactive} from 'vue';
    import Calculadora from './components/Calculadora.vue';
  


    const estado = reactive({
        num1:0,
        num2:0,
        operation: 'adicao',
  })


function result(){
const {operation,num1,num2} = estado;
switch (operation) {
    case 'adicao':
      return  num1 + num2
      case 'subtracao':
      return  num1 - num2
      case 'multiplicacao':
      return  num1 * num2
      case 'divisao':
      return  (num1 / num2).toFixed(5)
}

}

</script>

<template>

<Calculadora :numero1="event=> estado.num1 = Number(event.target.value)" :numero2="event=> estado.num2 = Number(event.target.value)"  :operacao="event => estado.operation = event.target.value" :resultado="result()" :condicao="estado.num1 && estado.num2 >= 0"/>
    
 
</template>

<style scoped>

</style>
