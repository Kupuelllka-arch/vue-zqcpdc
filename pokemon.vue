<template>
<div>
<div class ="card">
<img :src='require("/images/"+id+".png")'>
<p>{{name}}</p>
</div>
</div>
</template>
<script>

export default {
  props: ["name","id","abilities"],
  data: function(){
   return {
   }
  },
  methods: {}
},

</script>
<style>
.card {
	height: 60vh;
	width: 35vw;
	display:flex;
	flex-direction:column;
	align-items:center;
	border:20px solid #9fff9c;
	padding: 5px 5px;
}

</style>