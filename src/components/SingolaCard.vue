<script>

export default{
    name: "SingolaCard",
    props: ["datiSingolaCard"]
}

</script>

<template>
    <div class="card">
        <img :src="datiSingolaCard.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body text-center">
            <h5 class="card-title">{{ datiSingolaCard.name }}</h5>
            <span class="card-text">{{ datiSingolaCard.archetype }}</span>
        </div>
    </div>
</template>


<style scoped>

.card-body{
    background-color: rgb(212,143,56);
}

h5{
    color: white;
}

</style>