<script>
import Todo from "./components/Todo.vue";

export default {
    components: {
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
    methods: {},
};
</script>

<template>
    <div class="wrap">
        <Todo :todos="todos" />
    </div>
</template>

<style lang="scss" scoped>
.wrap {
}
</style>
