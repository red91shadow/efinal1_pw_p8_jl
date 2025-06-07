<template>
  <div v-if="valor" class="PantallaDerrota">
    <h2>Ha utilizado tus 5 intentos</h2>
    <h2>El juego a terminado, intentolo otra vez</h2>
  </div>
</template>

<script>
export default {
  props: {
    valorDerrota: {
      type: Boolean,
      required: true,
    },
  },

  data() {
    return {
        valor: this.valorDerrota,
      
    };
  },
};
</script>

<style>
</style>