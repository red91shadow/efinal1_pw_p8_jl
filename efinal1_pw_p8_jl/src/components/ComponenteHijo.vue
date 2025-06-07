<template>
  <div class="container">
    <img :src="imagenes" alt="No se puede mostrar la imagen" />
    <p>{{nombre}}</p>
  </div>
</template>

<script>
export default {
  props: {
    imagenes: {
      type: Number,
      required: true,
    },

    texto: {
      type: String,
      required: true,
    },

    
  },
  data() {
    return {
        nombre: this.texto,
      
    };
  },
};
</script>

<style>
</style>