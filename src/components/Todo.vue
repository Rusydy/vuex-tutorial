<template>
    <div id="todo">
        <div id="todos">
            <span 
            :class="{completed: todo.completed}"
            @click="toggleTodoStatus(todo)"
            >
                {{ todo.title }}
            </span>
            <button @click="deleteTodo(todo)">Delete</button>
        </div>
    </div>
</template>

<script>
import { mapActions } from "vuex"
export default {
    props: ["todo"],

    methods: {
        ...mapActions({
            deleteTodo: "deleteTodo",
            toggleTodoStatus: "toggleTodoStatus"
        }),

        // deleteTodo() {
        //     this.$store.dispatch('deleteTodo', this.todo)
        // },
        // toggleTodoStatus(){
        //     this.$store.dispatch('toggleTodoStatus', this.todo)
        // },
    }
}
</script>

<style scoped>
#todo{
    width: 250px;
    margin: 5px auto;
}

#todo #todos{
    display: flex;
    justify-content: space-between;
}

#todo #todos .completed {
    text-decoration: line-through;
}
</style>