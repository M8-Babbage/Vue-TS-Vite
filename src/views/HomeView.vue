<template>
  <!-- Implementación del componente Button con sus props y emits -->
  <Button @onClick="clickButton" label="Home View" color="red"></Button>
</template>

<script setup lang="ts">
// Importación del componente común Button
import Button from "@/commons/Button.vue";

// Función que recibe la emisión del evento onClick del componente Button
function clickButton(event: MouseEvent, color: string): void {
  console.log(event);
  console.log(color);
}
</script>
