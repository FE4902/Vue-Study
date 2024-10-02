<script setup>
import { ref } from "vue";

const emit = defineEmits(["insertTodo"]);

const text = ref("");

const handleClick = () => {
    emit("insertTodo", text.value);
    text.value = "";
};
</script>

<template>
    <div class="header">
        <input class="header__input" type="text" v-model="text" />
        <button class="header__button" @click="handleClick()">입력</button>
    </div>
</template>

<style lang="scss" scoped>
.header {
    display: flex;
    align-content: center;
    padding-bottom: 16px;

    &__input {
        flex: 1;
        min-width: 0;
        border: 1px solid black;
        border-right: 0;
        padding: 4px 8px;
    }

    &__button {
        border: 1px solid black;
        padding: 4px 8px;

        &:hover {
            color: white;
            background-color: black;
        }
    }
}
</style>
