<template>

    <div v-if="valor" class="PantallaVictoria">
      <h2>Puntaje: {{ puntaje }}</h2>
      <h3>Felicidades hasganado un premio de $10.000,00</h3>
    </div>

  
</template>

<script>
export default {
    props: {
    valorVictoria: {
      type: Boolean,
      required: true,
    },

    puntaje:{
        type:Number,
        required:true,
    }
  },

  data() {
    return {
        valor: this.valorDerrota,
        puntaj: this.puntaje
      
    };
  },

}
</script>

<style>

</style>