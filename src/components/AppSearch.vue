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
<select class="form-select w-25 mb-4 text-primary fw-bolder border-primary" aria-label="Default select example" @change="$emit('performSearch')" v-model="store.inputType">
  <option selected>Select a new archetype:</option>
  <option value="1">Alien</option>
  <option value="2">Ally of Justice</option>
  <option value="3">Ancient Gear</option>
  <option value="4">Blue-Eyes</option>
  <option value="5">Branded</option>
  <option value="6">Despia</option>
</select>
</template>

<style scoped lang="scss">
</style>