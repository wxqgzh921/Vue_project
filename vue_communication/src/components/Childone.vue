<template>
  <div class="childone">
    <div>我的名字是{{msg}}</div>
    <button @click='changeCount'>改变Count</button></br>
    <input v-model ="sex" />
    <button @click="giveB">传递给他的兄弟组件(childtwo)</button>
  </div>
</template>

<script>
import Bus from '../assets/js/bus.js'

export default {
  name: 'childone',
  props: ['msg'],
  data(){
    return{
      count:0,
      sex:''
    }
  },
  methods:{
    changeCount(){
      this.count += 1;
      this.$emit('changeCount')
    },
    giveB(){
      Bus.$emit('giveB',this.sex);
    }
  }
}
</script>


<style >

</style>
