<template>
    <div class="row text-center">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
                <label for="todoText">Add new ToDo</label>
                <textarea id="todoText" class="form-control" rows=3 v-model="todo"></textarea>
            </div>

            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
                <button class="btn btn-primary btn-block" @click.prevent="createTodo">Add ToDo</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                todo: ''
            };
        },
        methods: {
            createTodo() {
                this.$emit('todoAdded', this.todo);
                this.todo = '';
            }
        }
    };
</script>

<style lang="scss">
</style>