<template>
  <button @click="handleClick" :style="createButtonStyles()">
    {{ props.label }}
  </button>
</template>

<script setup lang="ts">
// Definimos las propiedades que va a recibir el componente
const props = defineProps({
  label: {
    type: String,
    required: true,
  },
  color: {
    type: String,
    required: false,
  },
});

// Definimos los eventos que va a emitir el componente
const emits = defineEmits({
  onClick: null,
});

// Función para cuando se haga click en el botón
function handleClick(event: MouseEvent) {
  // Emitimos el evento onClick con la información del evento, y el color
  emits("onClick", event, props.color);
}

// Retornamos los estilos de manera dinámica usando las props
function createButtonStyles() {
  return {
    color: props.color ? props.color : "black",
  };
}
</script>

<style scoped></style>
