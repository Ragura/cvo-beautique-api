<template>
    <main class="producten">
        <h1>Onze producten</h1>
        <div class="producten-lijst">
            <router-link tag="div" :to="`producten/${product.id}`" class="product" v-for="product of producten" :key="product.id">
                <div class="product-header">{{ product.naam }}</div>
                <div class="product-afbeelding">
                    <img :src="maakAfbeeldingUrl(product)" :alt="product.naam">
                </div>
                <div class="product-prijs">
                    {{ "€" + product.prijs }}
                </div>
            </router-link>
        </div>
    </main>
</template>

<script>
import { producten, categories } from "@/producten.js";

export default {
    data() {
        return {
            categories,
            producten,
            baseUrl: process.env.BASE_URL
        }
    },
    methods: {
        maakAfbeeldingUrl(product) {
            return `${this.baseUrl}producten/${product.categorie}/${product.afbeelding}`;
        }
    }
}
</script>

<style scoped>
.producten {
    display: flex;
    justify-content: center;
}

h1 {
    font-size: 8rem;
    color: #41B883;
}

.producten-lijst {
    margin-top: 7rem;
    width: 80%;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr) );
    /* grid-template-columns: repeat(5, 1fr ); */
    justify-items: center;
    column-gap: 5rem;
    row-gap: 5rem;
    
}

.product {
    border: 1px solid black;
    width: 100%;
    text-align: center;
    cursor: pointer;
}

.product-header {
    border-bottom: 1px solid black;
    background-color: #8FD5B5;
    color: white;
    font-size: 2rem;
}

.product-afbeelding {
    padding: 2rem;
}

.product-afbeelding img {
    max-width: 100%;
    max-height: 300px;
}

.product-prijs {
    padding: 1rem;
}
</style>
