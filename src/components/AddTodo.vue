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
    <input class="input_elem" v-model="mess" placeholder="Пожалуйста, введите новое задание" v-on:keydown.enter="addNewTodo(mess)"/>
</template>

<style>
.input_elem{
    display: flex;
    justify-content: center;
    margin: 20px 400px;
    width: 35%;
    box-shadow: 5px 5px 5px black;
}

</style>