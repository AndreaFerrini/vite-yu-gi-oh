<script>

export default{
    name: "SingolaCard",
    props: ["datiSingolaCard"]
}

</script>

<template>
    <div class="card">
        <img :src="datiSingolaCard.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ datiSingolaCard.name }}</h5>
            <span class="card-text">{{ datiSingolaCard.archetype }}</span>
        </div>
    </div>
</template>


<style scoped>

</style>