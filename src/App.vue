<script>
import Header from "./components/Header.vue";
import Todo from "./components/Todo.vue";

export default {
    components: {
        Header,
        Todo,
    },
    data() {
        return {
            todos: [
                { id: 1, text: "방 청소", isDone: true },
                { id: 2, text: "신발 정리", isDone: false },
                { id: 3, text: "코딩 공부", isDone: false },
            ],
        };
    },
    methods: {
        insertTodo(text) {
            this.todos = [...this.todos, { id: 4, text, isDone: false }];
        },
    },
};
</script>

<template>
    <div class="wrap">
        <Header @insertTodo="insertTodo" />
        <Todo :todos="todos" />
    </div>
</template>

<style lang="scss" scoped>
.wrap {
    padding: 16px;
    margin: 16px;
    border: 1px solid black;
}
</style>
