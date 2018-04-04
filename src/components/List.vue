<template>
  <div>
    <div class="div">
      待办：
      <ul>
        <li v-for="(item,index) in list" :key="item">
          <span>{{item}}</span>
          &nbsp;&nbsp;
          <button v-on:click="iscomplete(index)">已完成</button>
          &nbsp;
          <button v-on:click="remove(index)">删除</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    props:['list','islist','inputValue'],
    methods:{
      remove(index){
        this.list.splice(index, 1);
      },
      iscomplete(index){
        const item = this.list[index]
        this.list.splice(index, 1);
        this.islist.push(item)
      }
    }
  }
</script>

<style scoped>

</style>
