<template>
    <main class="producten">
        <h1>Onze producten</h1>
        <div class="filters">
            <label for="filter_categorie">
                Selecteer een categorie:
            </label>
            <select id="filter_categorie" v-model="gekozenCategorie">
                <option v-for="categorie in categories" :key="categorie" :value="categorie">
                    {{ categorie }}
                </option>
            </select>
        </div>
        <div class="producten-lijst">
            <router-link tag="div" :to="`producten/${product.id}`" class="product" v-for="product of gefilterdeProducten" :key="product.id">
                <div class="product-header">{{ product.naam }}</div>
                <figure class="product-afbeelding">
                    <img :src="maakAfbeeldingUrl(product)" :alt="`Afbeelding van ${product.naam}`">
                    <figcaption>{{ "€" + product.prijs }}</figcaption>
                </figure>
            </router-link>
        </div>
    </main>
</template>

<script>
import { producten, categories } from "@/producten.js";

export default {
    data() {
        return {
            categories: ["Alles", ...categories],
            producten,
            baseUrl: process.env.BASE_URL,
            gekozenCategorie: ""
        }
    },
    methods: {
        maakAfbeeldingUrl(product) {
            return `${this.baseUrl}producten/${product.categorie}/${product.afbeelding}`;
        }
    },
    computed: {
        gefilterdeProducten() {
            if (this.gekozenCategorie == "Alles") return this.producten;

            return this.producten.filter(product => 
                product.categorie === this.gekozenCategorie
            );
        }
    },
    created() {
        this.gekozenCategorie = this.categories[0];
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

.filters {
    margin-top: 2rem;
}

.filters select {
    font: inherit;
}

.producten-lijst {
    margin-top: 7rem;
    width: 80%;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr) );
    /* grid-template-columns: repeat(5, 300px); */
    justify-content: center;
    column-gap: 5rem;
    row-gap: 5rem;
}

.product {
    border: 1px solid black;
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
    padding-bottom: 1rem;
}

.product-afbeelding img {
    /* max-width: 100%; */
    height: 300px;
    /* max-height: 300px; */
}

.product-afbeelding figcaption {
    font-weight: bold;
    border-top: 1px solid rgba(65, 184, 131, 0.6);
    margin-top: 1rem;
    padding-top: 0.3rem;
}

.product-prijs {
    padding: 1rem;
}
</style>
