<template>
    <div class="row" style="padding-top: 50px">
        <todo-item
            v-for="(todo, index) in todos"
            key="{{index + todo.toLowerCase()}}"
            @click.native="deleteTodo(index)">
                {{ todo }}
        </todo-item>
    </div>
</template>

<script>
    import TodoItem from './TodoItem.vue';

    export default {
        props: ['todos'],
        components: {
            todoItem: TodoItem
        },
        methods: {
            deleteTodo(index) {
                this.$emit('todoDeleted', index);
            }
        }
    };
</script>

<style lang="scss"></style>