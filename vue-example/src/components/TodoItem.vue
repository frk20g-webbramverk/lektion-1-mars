<template>
  <li v-on:click="update">{{ task }}</li>
</template>

<script>
export default {
    name: 'todo-item',
    props: {
        todo: Object
    },
    computed: {
        task() {
            return 'Task: ' + this.todo.task + ' Done: ' + this.todo.done ;
        }
    },
    methods: {
        update: function() {
            this.$emit('done', this.task);
        }
    }
}
</script>

<style>

</style>