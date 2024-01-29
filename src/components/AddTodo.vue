<script>
    export default{
        methods:{
            addNewTodo(title)
             {
      this.$emit('addNewTodo', title)
            },
        }
    }
</script>

<template>
    <input class="input_elem" v-model="mess" placeholder="Пожалуйста, введите новое задание" v-on:keyup.enter="addNewTodo(mess)"/>
</template>

<style>

</style>