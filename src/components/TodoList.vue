<template>
  <div>
    <h2>TodoList</h2>
    <ul>
      <TodoListItem
        v-for="item in list"
        :item-data="item"
        :key="item.id"
        @delete="deleteList"
        @update="updateList"
      />
    </ul>
    <TodoListInput @add="addList"/>
  </div>
</template>

<script>
import TodoListInput from './TodoListInput'
import TodoListItem from './TodoListItem'

export default {
  data() {
    return {
      id: 2,
      list: [
        {id:0, text: '밥먹기', done: true},
        {id:1, text: '잠자기', done: false},
        {id:2, text: '놀기', done: false}
      ]
    }
  },
  components: {
    TodoListInput,
    TodoListItem
  },
  methods: {
    addList(val) {
      this.list.push({
        id:++this.id,
        text: val,
        done: false
        });
    },
    deleteList(id) {
      this.list = this.list.filter(item => item.id !== id);
    },
    updateList(val) {
      const {id, value} = val;
      this.list = this.list.map(item => {
        if(item.id === id){
          return {...item, done: value}
        }else {
          return item;
        }
      });
    }
  }
}
</script>

<style>

</style>
