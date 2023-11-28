<script>
import AppCount from "./AppCount.vue";
import AppList from "./AppList.vue"
export default {
    components: { AppCount, AppList },
} 
</script>

<template>
    <div class="ms_container">
        <div class="container bg-white p-4">
            <AppCount />
            <AppList />
        </div>
    </div>
</template>

<style lang="scss" scoped>
.ms_container{
    background-color: orange;
    width: 100%;
    padding: 40px;
}
</style>