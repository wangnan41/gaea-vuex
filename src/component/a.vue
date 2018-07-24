<template>
	<div class="wrapp">
		<h1>Vuex demo</h1>
		<p>a:{{aNum}}</p>
		<p>3倍增加后的a:{{aNum}}</p>
		<input  type="button" value="增加"  @click="addSync(5)"/>
	</div>
</template>

<script>
	import {mapState, mapActions,mapMutations} from 'vuex';
	export default {
		data(){
	        return{
	        }
	    },
		computed:mapState({
				aNum:state=>state.a.num, 
			}),
		methods:{
			...mapActions({
				addSync:'a/increase' //this.addSync 映射 this.$store.dispatch('a/increase')
			}),
			...mapMutations({
				add:'a/INCREASE'//this.add 映射 this.$store.commit('a/INCREASE')
			})
		},
		created(){

		},
		mounted(){
			this.add(3);
			
		},
		destroyed(){

		}
	}
	
</script>

<style lang="scss" >
	.wrapp{
		font-size:14px;
	}
	input{
		background: #ccc;
	}
	
</style>