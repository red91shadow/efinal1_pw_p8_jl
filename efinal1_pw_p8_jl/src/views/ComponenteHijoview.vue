<template>
  <div class="container">

    <div class="titulos">
      <h2>Punta:</h2>
      <h2>Intento:</h2>
    </div>


    <div class="imagenes">
      <componente-hijo :imagenes="imagenNegra" />
      <componente-hijo :imagenes="imagenNegra" />
      <componente-hijo :imagenes="imagenNegra" />
    </div>
  </div>
</template>

<script>
import ComponenteHijo from "../components/ComponenteHijo.vue";
export default {
  components: { ComponenteHijo },
  data() {
    return {
      
      image: [
        {
          id: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/1.png",
        },
        {
          id: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/2.png",
        },
        {
          id: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/3.png",
        },
      ],
      imagenesPokemon: [
        {
          id: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/1.png",
        },
        {
          id: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/2.png",
        },
        {
          id: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/3.png",
        },
      ],

      imagenNegra: "https://placehold.co/200x200/000000/000000.png",
    };
  },
};
</script>

<style scoped>

.container{
  margin-top: 6px;
}

.titulos{
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 200px;
  margin-bottom: 15px;
}


.imagenes{
  display: flex;
  flex-direction: row;
  gap: 15px;
  justify-content: center;
  
}
</style>