<script>
import CardsArea from "./CardsArea.vue"



export default{
    name: "MainComp",
    components: {
        CardsArea,
    }
}

</script>

<template>
    <main class="py-3">
        <div class="container bg-white py-3">
            <CardsArea/>
        </div>
    </main>
</template>

<style scoped>

main{
    background-color: rgb(212,143,56);
}

</style>