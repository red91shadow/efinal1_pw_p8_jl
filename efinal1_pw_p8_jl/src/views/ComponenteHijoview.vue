<template>
  <div class="container">
    <div v-if="sigeJugando" class="juego">
      <div class="titulos">
        <h2>Punta:</h2>
        <h2>Intento:</h2>
      </div>

      <div class="imagenes">
        <componente-hijo :imagenes="imagenNegra1" :texto="texto1" />
        <componente-hijo :imagenes="imagenNegra2" :texto="texto2" />
        <componente-hijo :imagenes="imagenNegra3" :texto="texto3" />
      </div>

      <button @click="comenzarJuego()">JUGAR</button>
    </div>

    <pantallavictoria :puntaje="this.puntaje" :valorVictoria="ganoElJuego" />
    <pantalladerrota :valorDerrota="elJuegoTermino" />
  </div>
</template>

<script>
import Pantallavictoria from "@/components/Pantallavictoria.vue";
import { PokemonCliente } from "../clients/PokemonClient.js";

import ComponenteHijo from "../components/ComponenteHijo.vue";
import Pantalladerrota from "@/components/Pantalladerrota.vue";
export default {
  components: { ComponenteHijo, Pantallavictoria, Pantalladerrota },
  data() {
    return {
      puntaje: 0,
      Intentos: 0,
      elJuegoTermino: false,
      ganoElJuego: false,
      sigeJugando: true,
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

      imagenNegra1: "https://placehold.co/200x200/000000/000000.png",
      imagenNegra2: "https://placehold.co/200x200/000000/000000.png",
      imagenNegra3: "https://placehold.co/200x200/000000/000000.png",

      texto1: "xxxxxxxxxxxx",
      texto2: "xxxxxxxxxxxx",
      texto3: "xxxxxxxxxxxx",
    };
  },

  methodos: {
    comenzarJuego() {},

    async obtenerPokemon(id) {
      try {
        const respuesta = await fetch(
          `https://pokeapi.co/api/v2/pokemon/${id}`
        );
        if (!respuesta.ok) throw new Error("No se encontró el Pokémon");
        const datos = await respuesta.json();

        return datos.name;
      } catch (error) {
        console.error(error);
        return null;
      }
    },
  },
};
</script>

<style scoped>
.container {
  margin-top: 6px;
}

.titulos {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 200px;
  margin-bottom: 15px;
}

.imagenes {
  display: flex;
  flex-direction: row;
  gap: 15px;
  justify-content: center;
}

button {
  padding: 10px 50px;
  font-size: 20px;
}

.PantallaVictoria {
  color: rgb(58, 58, 238);
}

.PantallaDerrota {
  color: red;
}
</style>