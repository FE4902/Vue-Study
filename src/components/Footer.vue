<script setup>
const props = defineProps({ filter: Array });
const emit = defineEmits(["handleFilter", "clearAll"]);
</script>

<template>
    <footer class="footer">
        <div class="footer__filter">
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
        <button class="footer__button" @click="emit('clearAll')">
            Clear All
        </button>
    </footer>
</template>

<style lang="scss" scoped>
.footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
    padding-top: 16px;

    &__filter {
        display: flex;
        align-content: center;
        gap: 4px;
    }

    &__button {
        width: 100px;
        border: 1px solid black;
        padding: 2px 4px;

        &.active {
            color: white;
            background-color: black;
        }

        &:hover {
            color: white;
            background-color: black;
        }
    }
}
</style>
