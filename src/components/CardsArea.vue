<script>

import { store } from '../store'
import SingolaCard from "./SingolaCard.vue"

export default{
    name: "CardsArea",
    components: {
        SingolaCard
    },
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <div class="row">
        <div v-for="(elem, index) in store.arrayCarte" :key="index" class="col-3">
            <SingolaCard :datiSingolaCard="elem" />
        </div>

    </div>
</template>

<style scoped>

</style>