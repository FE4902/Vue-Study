<script>
export default {
    props: {
        todos: Array,
    },
};
</script>

<template>
    <ul class="todo">
        <li class="todo__item" v-for="todo in todos" :key="todo.id">
            <span class="todo__text" :class="{ complete: todo.isDone }">{{
                todo.text
            }}</span>
            <input
                class="todo__checkbox"
                type="checkbox"
                v-model="todo.isDone"
            />
        </li>
    </ul>
</template>

<style lang="scss" scoped>
.todo {
    &__item {
        display: flex;
        align-content: center;
        gap: 8px;
    }

    &__text {
        &.complete {
            text-decoration: line-through;
        }
    }

    &__checkbox {
        accent-color: black;
    }
}
</style>
