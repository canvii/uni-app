<template>
	

	
	<view class="content">
			
		<view class="text-area" @touchend="touchend" @touchcancel="zero"   @touchmove="joystick($event)">
			
		
				<image class="outerImg" src="../../static/out.png" v-bind:style="{height:outheight+'px',width:outWidth+'px'}"></image>
			
			
				<image class="innerImg"  src="../../static/in.png" v-bind:style="{'margin-left':centerX+'px','margin-top':centerY+'px',height:innerheight+'px',width:innerWidth+'px'}" ></image>
		
		
			
		</view>
	</view>
</template> 

<script>
	export default {
		data() {
			
			return {
				title: 'Hello',
				centerX:0,
				centerY:0,
				innerWidth:100,
				innerheight:100,
				outWidth:100,
				outheight:100,
				radius:50
				
			}
		},
		onLoad() {

		},
		methods: {
			
			joystick(e){
				 // e.currentTarget.offsetLeft
				let refToX=Number(e.touches[0].pageX -this.$data.radius).toFixed(1)
				let refToY=Number(e.touches[0].pageY -this.$data.radius).toFixed(1)
				
				
				
			
				this.centerX=refToX;
				this.centerY=refToY;
				// console.log((e.touches[0].pageX)+' : '+(e.touches[0].pageY));
			},
			zero(){
				this.centerX=0;
				this.centerY=0;
			},
		
			
			touchend(){
				this.centerX=0;
				this.centerY=0;
			}
			
			
		}
		
	}
	
</script>

<style>

	.outerImg {
		position:absolute;
		mode:"aspectFill";
		
	}
	.innerImg{
		position: relative;
		mode:"aspectFill";
		
		
	}
	
	.content {
		/* display: flex; */
		/* align-items: flex-start; */
		/* justify-content: left; */
		margin-left: 10px;
		margin-top: 10px;
		position: absolute;
	}

	

	.text-area {
		/* display: flex; */
		background-color: #808080;
		position: absolute;

		
		
	}

	.title {
		font-size: 36px;
		color: #8f8f94;
	}
	*{
	padding:0;            /*清除内边距*/
	
	margin:0;              /*清除外边距*/
	
	}
</style>
