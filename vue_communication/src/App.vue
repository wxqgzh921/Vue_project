<template>
  <div id="app">
  		<label>name: </label><input v-model="msg"/></br>
  		<label>age: &nbsp;&nbsp; </label><input v-model="age"/></br>
      <span>点击次数：{{ count }}</span>
      <hr/>
      <Childone :msg="msg" v-on:changeCount="changeCountP"></Childone>
      <hr/>
      <Childtwo :age="age" ></Childtwo>
      </br>
      </br>
      </br>
      <router-link to="./one">点我1</router-link>
      <router-link to="./two">点我2</router-link>

      <router-view></router-view>
  </div>
</template>

<script>
import Childone from './components/Childone'
import Childtwo from './components/Childtwo'

export default {
  name: 'app',
  components:{
  	Childone,
  	Childtwo
  },
  data(){
  	return{
  		msg:'',
  		age:'',
  		count:0
  	}
  },
  methods:{
  	changeCountP(){
  		this.count += 1;
  	}
  }
}
</script>

<style>
	div{ margin-top:10px; margin-bottom:10px;}
  input{ margin-bottom:5px;margin-top:5px;}
</style>
