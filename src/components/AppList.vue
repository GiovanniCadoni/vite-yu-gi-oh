<script>
import { store } from "../store.js";
//import AppCard from "./AppCard.vue";

export default {
    data() {
        return {
            store,
        };
    },
    //components: AppCard,
};
</script>

<template>
    <div class="container bg-warning">
        <div class="row row-cols-5 py-3">

            <div class="col mb-5" v-for="card in store.cards" :key="card.id">
                <!-- <AppCard :card="card" /> -->
                <div class="card p-2 text-center">
                    <img class="card-img-top" :src="card.card_images[0].image_url_small" alt=""/>
                    <div class="card-text">
                        <h3 class="card-header fs-5 fw-bolder">{{ card.name }}</h3>
                        <p class="card-text py-2 text-primary">Archetype: {{ card.archetype === undefined ? "None" : card.archetype }}</p>
                    </div>
                </div>
            </div>
            
        </div>
    </div>
    
</template>

<style lang="scss" scoped>
</style>