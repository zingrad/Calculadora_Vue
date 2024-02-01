<script setup>
     const props = defineProps(['numero1','numero2','operacao','resultado','condicao'])
</script>


<template>
    <div class="container p-4 mt-5 bg-primary-subtle rounded">
     <h1>Calculadora Vue Js</h1>
     <div class="row mt-5">
         <div class="col d-flex">
             <input   @keyup="props.numero1" class="me-2 form-control w-25" type="number" >
             <input   @keyup="props.numero2" class="me-2 form-control w-25" type="number" >
             <select @change="props.operacao" class="me-2 rounded-3" >
                 <option value="adicao">Adição</option>
                 <option value="subtracao">Subtração</option>
                 <option value="multiplicacao">Multiplicação</option>
                 <option value="divisao">Divisão</option>
             </select>
         </div>
     <span class="text-success" v-if="props.condicao">{{ props.resultado}}</span>
     <span v-else>Digite um número</span>
     </div>
    </div>
 </template>