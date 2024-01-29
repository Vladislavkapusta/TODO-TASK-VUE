<script>
    export default{
        props:{
            title: String,
            completed: Boolean,
            id: Number
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
    <div v-if="completed" class=" todo_item task green" @click="changeTodo(id)" @dblclick="removeTodo(id)" >
    {{ title }}
    {{ completed }}     
    </div>
    <div v-else="!completed" class="todo_item task red" @click="changeTodo(id)" @dblclick="removeTodo(id)" >
    {{ title }}
    {{ completed }}
    </div>

</template>

<style scoped>
    .task{
        width: 80%;
        height: 100px;
    }
    .green{
        background-color: green;
    }
    .red{
        background-color: red;
    }
</style>