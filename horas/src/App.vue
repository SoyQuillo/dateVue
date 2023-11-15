<script setup>

import { ref } from 'vue'

let variableRefName = ref('')
let variableRefApellido = ref('')
let variableRefFecha = ref('')
let variableRefPhone = ref ('')
let edad = 0;
let dividirpor = 31536000000;
let totalEdad = 0;
let holaquehacesxd = 1000*60*60*24*365;

function calculateAge(){

  if (!variableRefFecha.value){

    return 'Ingresa algo FANTASMA';

  }

  const timeActual = new Date ()

  console.log(timeActual)

  let newDate = new Date(variableRefFecha.value);

  edad = timeActual - newDate;

  
  totalEdad = Math.floor(edad / dividirpor);

  return totalEdad;


}
</script>

<template>

<div>
  <input v-model="variableRefName" class="Nombre" type="text"> <h1>{{ variableRefName }}</h1>
  <input v-model="variableRefApellido" class="Apellido" type="text"><h1>{{ variableRefApellido }}</h1>
  <input v-model="variableRefFecha" class="fecha" type="date"> {{ calculateAge() }} <h1 v-if="variableRefFecha"></h1>
  <input v-model="variableRefPhone" class="phone" type="number">{{ variableRefPhone }}
</div>

</template>

<style scoped>

</style>
