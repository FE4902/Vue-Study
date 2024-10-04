<script setup>
const props = defineProps({ filter: Array });
const emit = defineEmits(["handleFilter", "clearTodo"]);
</script>

<template>
    <footer class="footer">
        <div class="footer__buttons">
            <button
                class="footer__button"
                :class="{ active: props.filter === 'ALL' }"
                @click="emit('handleFilter', 'ALL')"
            >
                All
            </button>
            <button
                class="footer__button"
                :class="{ active: props.filter === 'ACTIVE' }"
                @click="emit('handleFilter', 'ACTIVE')"
            >
                Active
            </button>
            <button
                class="footer__button"
                :class="{ active: props.filter === 'COMPLETE' }"
                @click="emit('handleFilter', 'COMPLETE')"
            >
                Complete
            </button>
        </div>
        <div class="footer__buttons">
            <button
                class="footer__button"
                @click="emit('clearTodo', 'COMPLETE')"
            >
                Clear Complete
            </button>
            <button class="footer__button" @click="emit('clearTodo', 'ALL')">
                Clear All
            </button>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
.footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
    padding-top: 16px;

    &__buttons {
        display: flex;
        align-content: center;
        gap: 4px;
    }

    &__button {
        min-width: 100px;
        border: 1px solid black;
        padding: 4px 8px;
        line-height: normal;

        &:hover,
        &.active {
            color: white;
            background-color: black;
        }
    }
}
</style>
