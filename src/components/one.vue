<template>
  <div class="hello1">
111111
<van-radio-group v-model="radio">
  <van-radio name="1">
    <van-field  v-model="timerName" placeholder="请选择间隔时间" @click="choose=true" readonly></van-field>
  </van-radio>
  <van-radio name="2">
    <van-field label="开始时间" readonly @click="choose1=true">

    </van-field>
    <van-field label="结束时间" readonly >
    </van-field>
  </van-radio>
</van-radio-group>
<van-action-sheet v-model="choose" :actions="arr" @select="onSelect" ></van-action-sheet>
<van-popup v-model="choose1" position="bottom">
   <van-datetime-picker v-model="currentDate" :min-date="minDate" :max-date="maxDate" @cancel="cancel"></van-datetime-picker>
</van-popup>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      show:false,
      radio:"1",
      timerValue:'',
      timerName:'',
      choose:false,
      arr:[{id:0,name:"1小时"},{id:1,name:"2小时"},{id:2,name:"3小时"}],

      choose1:false,

      minDate:new Date(2000,1,1),
      maxDate:new Date(2025,1,1),
      currentDate:new Date()
    }
  },
  methods:{
    onSelect(i){
      console.log(i)
      this.choose=false
      this.timerValue=i.id
      this.timerName=i.name
      console.log(2)
    },
    cancel(){
      console.log("取消")
      this.choose1=false

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
