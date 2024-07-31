<script>
export default {
    props: {
        todos: Array,
    },
    methods: {
        filter: () => {
            alert(1);
        },
        clearAll: () => {
            todos = [];
        },
    },
};
</script>

<template>
    <footer class="footer">
        <div class="footer__filter">
            <button class="footer__button" @click="filter()">All</button>
            <button class="footer__button">Active</button>
            <button class="footer__button">Complete</button>
        </div>
        <button class="footer__button" @click="clearAll()">Clear All</button>
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

        &:hover {
            color: white;
            background-color: black;
        }
    }
}
</style>
