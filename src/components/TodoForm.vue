<template>
    <div id="todoForm">
        <input type="text" v-model="newTodoItem"/>
        <button @click="addNewTodoItem()">Submit</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: ""
        }
    },

    methods: {
        addNewTodoItem() {
            this.$store.dispatch('addNewTodo', this.newTodoItem)
            this.newTodoItem = ""
        }
    }
}
</script>

<style>

</style>