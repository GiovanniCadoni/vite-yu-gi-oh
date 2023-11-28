<script>
import { store } from "../store.js";
export default {
    data() {
        return {
            store,
        };
    },
};
</script>

<template>
    <div class="p-3 fs-4">
        Trovate {{store.cards.length}} carte
    </div>
</template>

<style lang="scss" scoped>
div{
    background-color: black;
    padding: 10px;
    color: white;
    font-weight: bold;
}
</style>