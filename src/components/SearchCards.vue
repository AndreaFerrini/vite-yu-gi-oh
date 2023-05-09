<script>

import axios from "axios";
import { createHydrationRenderer } from "vue";
import { store } from "../store";

export default{
    name: "SearchCards",
    data() {
        return {
            store
        }
    },
    created() {
        axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php")
            .then( (res)=>{
                console.log(res.data)
                this.store.arrayArchetype = res.data
            })
    }
}

</script>

<template>

    <div class="sfondo-arancio">
        <select name="filter-cards" id="select-cards" v-model="store.valueArchetype" @change="$emit('nomeEmit')">
            <option :value="elem.archetype_name" v-for="(elem, index) in store.arrayArchetype"
             :key="index">{{ elem.archetype_name }}</option>
        </select>
    </div>

</template>

<style scoped>

.sfondo-arancio{
    background-color: rgb(212,143,56);
    padding-top: 10px;
}

select{
    border-radius: 5px;
    background-color: white;
    width: 15%;
    margin-left: 15%;
}

</style>