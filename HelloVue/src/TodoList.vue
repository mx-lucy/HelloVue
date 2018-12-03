<template>
  <div>
    <input v-model="inputValue"/>
    <button @click="addtodolist">Todolist</button>
    <a href="view/map/map.html">map</a>
    <p>{{inputValue}}</p>
    <ul>
      <todo-item
        v-for="(item,index) of list"
        :key="index"
        :index="index"
        :content="item"
        @delete="handleDetele"
      ></todo-item>
      <!--<li v-for="(item,index) of list" :key="index">{{item}}</li>-->
    </ul>

  </div>
</template>

<script>

import TodoItem from './components/TodoItem'


export default {
  components:{
    'todo-item':TodoItem
  },
  data:function () {
    return{
      inputValue:'',
      list:[]
    }

  },
  methods:{
    addtodolist:function () {
      this.list.push(this.inputValue)
      this.inputValue=''
    },
    handleDetele:function (index) {
      this.list.splice(index,1)
    }
  },
}
</script>

<style>

</style>
