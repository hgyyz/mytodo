<template>
    <div>
        <ul class="todo-main">
            <MyItem 
            v-for="todo in todos" 
            :key = "todo.id" 
            :todo = "todo" 
            :checkTodo = "checkTodo"
            :deleteTodo = "deleteTodo"/>
          </ul>
    </div>
</template>

<script>
    import MyItem from './MyItem.vue'
    export default {
        name: 'MyList',
       
        components: {
            MyItem
        },
        props: ["todos","checkTodo","deleteTodo"]
    }
</script>

<style scoped>

</style>