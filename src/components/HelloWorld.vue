<template>
  <div class="hello">
<div class="container">
  <div class="plus" @click="show=!show">+</div>
  <div class="top" style="background-color: #42B983;height:40px;">
    <ul>
      <li class="title" :class="{'on':active==0}" @click="selectActive(0)">管理</li>
      <li class="title" :class="{'on':active==1}" @click="selectActive(1)">化验</li>
      <li class="title" :class="{'on':active==2}" @click="selectActive(2)">巡检</li>
      <li class="title" :class="{'on':active==3}" @click="selectActive(3)">养护</li>
      <li class="title" :class="{'on':active==4}" @click="selectActive(4)">维修</li>
      <li class="title" :class="{'on':active==5}" @click="selectActive(5)">保养</li>
    </ul>

      <van-action-sheet v-model="show" :actions="plusList" />
  </div>
</div>
<div class="toggle">
<one v-if="active==1"></one>
<two v-if="active==2"></two>
<three v-if="active==3"></three>
<four v-if="active==4"></four>
<five v-if="active==5"></five>
</div>
  </div>
</template>

<script>
  import one from './one.vue'
  import two from './two.vue'
  import three from './three.vue'
  import four from './four.vue'
  import five from './five.vue'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      show:false,
      active:0,
      plusList:[{id:0,name:"报修"},{id:1,name:"维护"}]
    }
  },
  components:{
    one,two,three,four,five
  },
  methods:{
    selectActive(e){
      this.active=e
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
