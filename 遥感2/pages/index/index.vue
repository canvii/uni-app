<template>

	<view class="content">
		<button @click="get">点击</button>
		<joy-stick></joy-stick>
	</view>
</template> 

<script>
	export default{
		data(){
			return{
				
			}
		},
	
		
		methods: {
			get(){
				var a=uni.getConnectedWifi(),
					 
									console.log(a );
				       
			}
	
		}
	}
	
</script>

<style>
	*{
		margin: 0;
		padding: 0;
	}
</style>
