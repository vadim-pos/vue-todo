<template>
    <div class="container">
        <todo-progress-bar :todosCount="todos.length" :maxTodos="maxTodos"></todo-progress-bar>
        <todo-add @todoAdded="onTodoAdded"></todo-add>
        <todo-list :todos="todos" @todoDeleted="onTodoDeleted"></todo-list>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Click on ToDo to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import TodoList from './components/TodoList.vue';
    import AddTodoItem from './components/AddTodoItem.vue';
    import ProgressBar from './components/ProgressBar.vue';

    export default {
        data() {
            return {
                todos: [
                    'Walk the dog',
                    'Feed the cat'
                ],
                maxTodos: 10
            }
        },

        components: {
            todoList: TodoList,
            todoAdd: AddTodoItem,
            todoProgressBar: ProgressBar
        },

        methods: {
            onTodoAdded(todo) {
                if (this.todos.length >= this.maxTodos) {
                    return alert('Please delete quote first!');
                }
                this.todos.push(todo);
            },
            onTodoDeleted(index) {
                this.todos.splice(index, 1);
            }
        }
    }
</script>

<style lang="scss">

</style>
