<script setup>
import{onMounted, reactive, ref, computed} from 'vue'
import ListPokemons from '../components/ListPokemons.vue';


let baseUrlSvg = ref('https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/');
let allPokemons = reactive(ref());
let searchPokemonField = ref('');


onMounted(()=>{
  fetch('https://pokeapi.co/api/v2/pokemon?limit=151&offset=0')
  .then(res => res.json())
  .then(res => allPokemons.value = res.results)
})

const pokemonFilter = computed(()=>{
  if(allPokemons.value && searchPokemonField.value){
    return allPokemons.value.filter(pokemon=>
      pokemon.name.toLowerCase().includes(searchPokemonField.value.toLowerCase())
    )
  }

  return allPokemons.value
})

</script>

<template>
  <main>
    <div class="row">
      <div class="col-sm-12 col-md-6">
        <div class="card mt-4 ms-5" style="width: 18rem;">
              
              
              <img src="../assets/pokeball.png" class="card-img-top" alt="...">


              <div class="card-body">
                <h5 class="card-title">Card title</h5>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
              </div>

        </div>
      </div>
    

        <div class="col-sm-12 col-md-6 ">
          <div class="card mt-4 ms-5 me-5">
            <div class="card-body row">
              
              
              
              <div class="mb-3">
                <input 
                v-model="searchPokemonField"
                type="text" 
                class="form-control"  
                placeholder="Pesquisar..."/>
              </div>
                        
              
                <ListPokemons
                v-for="pokemon in pokemonFilter" 
                :key='pokemon.name'
                :name='pokemon.name'
                :baseUrlSvg="baseUrlSvg + pokemon.url.split('/')[6] +'.svg'"/>              
              
            
            
            
          </div>  
        </div>
      </div>
  </div>  
  </main>
</template>
