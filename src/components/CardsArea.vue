<script>

import { store } from '../store'

export default{
    name: "CardsArea",
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <div class="row">
        <div class="col-3">
            <div class="card">
                <img src="..." class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">Titolo carta</h5>
                    <span class="card-text">Archetipo</span>
                </div>
            </div>
        </div>

    </div>
</template>

<style scoped>
</style>