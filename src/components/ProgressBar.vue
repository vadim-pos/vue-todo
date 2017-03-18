<template>
    <div class="row">
        <h3>Todos Added</h3>
        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
            :style="{width: (todosCount / maxTodos) * 100 + '%' }">
                {{ todosCount }} / {{ maxTodos }}
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props: ['todosCount', 'maxTodos']
    };
</script>