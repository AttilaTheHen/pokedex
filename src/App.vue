<template>
  <div id="app">
    <h1>Pokedex</h1>
    <main>
      <section class="header">
        <Header
          :pokeFilter="chosenFilter"
        />
        <!-- using v-bind, pass down the variable 'filter', which I just assign here as "chosenFilter" -->
      </section>
      <section class="results">
        <Results
          :list="filtered"
        />
      </section>
    </main>
  </div>
</template>

<script>
import pokemon from '../pokemon.js';
import Header from './components/Header.vue';
import Results from './components/Results.vue';

export default {
  data() {
    return {
      list: pokemon,
      chosenFilter: {
        type: '',
        attack: '',
      }
    };
  },

  computed: {
    // filteredType() {
    //   let filteredPokemon = [];
    //   for(let i in this.list) {
    //     if(this.list[i].type_1 === this.chosenFilter.type) {
    //       filteredPokemon.push(this.list[i]);
    //     }
    //   }
    //   return filteredPokemon;
    // },
    // filteredAttack() {
    //   let filteredPokemon = [];
    //   for(let i in this.list) {
    //     if(this.list[i].attack >= this.chosenFilter.attack) {
    //       filteredPokemon.push(this.list[i]);
    //     }
    //   }
    //   return filteredPokemon;
    // }

    filtered() {
      return this.list.filter(pokemon => {
        
        return (pokemon.type_1 === '' || pokemon.type_1 === this.chosenFilter.type)
        && (pokemon.attack === '' || pokemon.attack >= this.chosenFilter.attack);
      });
    }
  },

  components: {
    Header,
    Results
  }
};
</script>

<style>
body {
  font-family: 'Avenir', sans-serif;
}
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background: #eee;
}

main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 90%;
  margin: auto;
}

.header {
  display: flex;
  background: lightsteelblue;
  width: 90%;
 
}

.results {
  background: peachpuff;
  width: 90%;
  overflow-y: auto;
  height: 700px;

}
h1 {
  font-size: 5em;
    color: rgb(255, 247, 0);
    line-height: 1em;
    text-shadow: 3px 5px 1px rgb(12, 27, 168);
    -webkit-text-stroke-color: rgb(3, 12, 247);
    -webkit-text-stroke-width: 3px;
    margin-bottom: 20px;
    margin-top: 20px;
    text-align: center;
}
</style>

filtered() {
  return animals.filter(function animal() {
    return (type === '' || animal.type === type)
  }
  }
}

function animal() {
  return (type === '' || animal.type === type)
}