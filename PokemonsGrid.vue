<template>
<div>
<ul id="default">
	<li v-for="item in pokemons">
	{{item.name}}
	<img :src='require("./public/"+item.id+".png")'>
	<p>Abilities</p>
	<ability :abilities="item.abilities"></ability>
  <pokemon :id="item.id" :name="item.name" :abilities="item.abilities">
</pokemon>
	</li>	
</ul>
</div>
</template>
<script>
import pokemon from './pokemon.vue'
import Abilities from './ability.vue'
export default {
  data: function(){
   return {
   pokemons:[]
   }
  },
  created() {
  fetch("https://pokeapi.co/api/v2/pokemon/?limit=15")
  .then(response=>response.json())
  .then(pokemons=>{const dat = pokemons.results
  let i = 0
  const data = []
  for (i;i<15;i++){
  data.push(fetch(dat[i].url)
  .then(response=>response.json()))
  }
  Promise.all(data)
  .then(result=>{
  this.pokemons=result
  console.log(result)
  })
  })
  },
  components: {
  pokemon : pokemon,
  ability: Abilities
  }
 }
</script>
<style>
</style>