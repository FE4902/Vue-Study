<script setup>
import Header from "./components/Header.vue";
import Todo from "./components/Todo.vue";
import Footer from "./components/Footer.vue";
import { ref } from "vue";

const todos = ref([
    { id: 1, text: "방 청소", isDone: true },
    { id: 2, text: "신발 정리", isDone: false },
    { id: 3, text: "코딩 공부", isDone: false },
]);

const insertTodo = (text) => {
    todos.value = [...todos.value, { id: 4, text, isDone: false }];
};

const clearAll = () => {
    todos.value = [];
};
</script>

<template>
    <div class="wrap">
        <Header @insertTodo="insertTodo" />
        <Todo :todos="todos" />
        <Footer @clearAll="clearAll" />
    </div>
</template>

<style lang="scss" scoped>
.wrap {
    padding: 16px;
    margin: 16px;
    border: 1px solid black;
}
</style>
