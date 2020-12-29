<template>
  <div id="app">
  	<button @click="model">执行modal函数</button>
    <slot><Model ref="mychild"></Model></slot>
  </div>
</template>

<script type="text/javascript">
	import Model from './components/Model'
	export default{
		name: 'App',
		data(){
			return{
				
			}
		},
		methods:{
			model(){
         this.$refs.mychild.showModal=true;
			}
		},
		components:{
			Model
		}
	}
</script>

<style>

</style>
