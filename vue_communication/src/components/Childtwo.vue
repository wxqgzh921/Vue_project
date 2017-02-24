<template>
	<div class="childtwo">
		<div>我的年龄是{{ age }}</div>
		<div>接收one 的数据 ：{{ sex }}</div>
	</div>
</template>

<script>
import Bus from '../assets/js/bus.js'

	export default{
		name:'childtwo',
		props:['age'],
		data(){
		    return{
		    	sex:''
		    }
		},
		mounted(){
			Bus.$on('giveB',function(sex){
				this.sex= sex
			}.bind(this))
		}
	}
</script>