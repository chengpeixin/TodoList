<template>
  <div>
    <div>
        已完成：
        <ul>
          <li v-for="(item,index) in islist" :key="item">
            <span>{{item}}</span>
          </li>
        </ul>
    </div>
  </div>
</template>

<script>
  export default {
    props:['islist']
  }
</script>

<style scoped>

</style>
