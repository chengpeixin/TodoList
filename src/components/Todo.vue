<template>
<div>
  <input type="text" v-model="inputValue">
  <button v-on:click="hadelBtnClick">提交</button>
  <List :list="list" :islist="islist" :inputValue="inputValue"></List>
  <hr>
  <br>
  <Isoklist :islist="islist"></Isoklist>

</div>
</template>

<script>
import List from "./List"
import Isoklist from "./Isoklist"
export default {
  name: 'Todo',
  data () {
    return {
      list:[],
      inputValue:'',
      islist:[]
    }
  },
  created(){
    Array.prototype.isKey=function(key){
      if (this.indexOf(key)!=-1){
        console.log('有')
        return true;
      }else {
        console.log('没有')
        return false;
      }
    }
  },
  methods:{
    hadelBtnClick(){
      if (this.inputValue==""){
        alert('不能输入空值')
        return;
      }
      if (this.list.isKey(this.inputValue)){
        alert('不能输入相同的')
        this.inputValue=""
        return;
      }
      this.list.push(this.inputValue);
      this.inputValue=""
    }
  },
  components:{
    List,
    Isoklist
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>

.div
 display block
 background red
 opacity 1
</style>
