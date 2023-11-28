<script>
import AppCount from "./AppCount.vue";
import AppList from "./AppList.vue";
import AppSearch from "./AppSearch.vue";
import { store } from "../store.js";
import axios from "axios";
export default {
    data() {
        return {
            store,
        };
    },
    components: { AppCount, AppList, AppSearch },
    methods: {
        inputSearch() {
            console.log("Funziona");
            if(this.store.inputType ==  1)
            {
                this.store.searchType = "Alien";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
                this.store.apiUrl = `${this.store.apiUrl}&archetype=${this.store.searchType}`;
            
            } else if (this.store.inputType == 2)
            {
                this.store.searchType = "Ally of justice";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
                this.store.apiUrl = `${this.store.apiUrl}&archetype=${this.store.searchType}`;

            } else if (this.store.inputType == 3)
            {
                this.store.searchType = "Ancient Gear";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
                this.store.apiUrl = `${this.store.apiUrl}&archetype=${this.store.searchType}`;

            } else if (this.store.inputType == 4)
            {
                this.store.searchType = "Blue-Eyes";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
                this.store.apiUrl = `${this.store.apiUrl}&archetype=${this.store.searchType}`;

            } else if (this.store.inputType == 5)
            {
                this.store.searchType = "Branded";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
                this.store.apiUrl = `${this.store.apiUrl}&archetype=${this.store.searchType}`;

            } else if (this.store.inputType == 6)
            {
                this.store.searchType = "Despia";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
                this.store.apiUrl = `${this.store.apiUrl}&archetype=${this.store.searchType}`;

            } else {
                this.store.searchType = "";
                this.store.apiUrl = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0";
            }
            axios
            .get(this.store.apiUrl, {
                
            })
            .then((resp) => {
                this.store.cards = resp.data.data;
            });
        },
    },
} 
</script>

<template>
    <div class="ms_container">
        <div class="container bg-white p-4">
            <AppSearch @performSearch="inputSearch" />
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