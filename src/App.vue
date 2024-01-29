<script>
  import AddTodo from './components/AddTodo.vue'
  import TodoList from './components/TodoList.vue'

  export default{
    data(){
      return{
        data:[
    {id: 1, title: 'Задача 1', completed: true},
    {id: 2, title: 'Задача 2', completed: false},
    {id: 3, title: 'Задача 3', completed: true},
            ]
      }
    },
    components:{
        AddTodo, TodoList
    },
    methods:{
    removeTodo(id){
this.data = this.data.filter((elem=>elem.id != id))
console.log('REMOVED', id)
  },
    changeTodo(id){
  let changedTasks = this.data.map(elem=>{
    if (elem.id === id){
      elem.completed = !elem.completed
    }
    return elem
  }, console.log('CHANGED', id)
      )
  this.data = changedTasks
},
addNewTodo(title){
  let newTodo = {
    id: Date.now(),
    completed: false,
    title: title
  }
  this.data = [...this.data, newTodo]
}
    }
  }
</script>

<template>
  <div>
      <AddTodo @addNewTodo="addNewTodo"></AddTodo>
      <TodoList
       :todos="data"
       @removeTodo = "removeTodo"
       @changeTodo= "changeTodo">
      </TodoList>
    </div>
</template>

<style>
  .todo_item{
    display: flex;
    flex-direction: column;

    margin: 20px 170px;
    padding: 10px;

    outline: 2px solid black;
    box-shadow: 5px 5px 5px black;
}


</style>