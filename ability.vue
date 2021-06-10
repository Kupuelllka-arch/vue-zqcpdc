<template>
<ul>
<li v-for="itm in abilities">
	{{itm.ability.name}}
</li>
</ul>
</template>
<script>
export default {
props: ['abilities'],
  data: function(){
   return {
  
   }
  },
 }
</script>
<style></style>