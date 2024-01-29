<script>
import TodoItem from './TodoItem.vue'
    export default{
        components:{
            TodoItem
        },
        props:{
            todos: Array
        },
        methods:{
            removeTodo(id)
             {
      this.$emit('removeTodo', id)
            },
            changeTodo(id)
             {
      this.$emit('changeTodo', id)
            },
        }
    }
</script>

<template>
    <div v-for="todo in todos">

    <TodoItem
    :title = "todo.title"
    :completed = "todo.completed"
    :id = "todo.id"
    @removeTodo = "removeTodo"
    @changeTodo= "changeTodo"
    >
    </TodoItem>
    </div>

</template>

<style>

</style>