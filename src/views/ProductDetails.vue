<template>
    <div class="product-details">
        <h4 class="terug">
            <span @click="$router.go(-1)">&lt; Terug</span>
        </h4>
        <div class="product-container">
            <div class="product-afbeelding">
                <img :src="maakAfbeeldingUrl(huidigProduct)" :alt="huidigProduct.naam">
            </div>
            <div class="product-gegevens-container">
                <!-- Container bestaat omdat CSS Grid alle kolommen van een rij even groot maakt -->
                <div class="product-gegevens">
                    <h2 class="product-titel">{{ huidigProduct.naam }}</h2>
                    <p class="product-beschrijving">{{ huidigProduct.beschrijving }}</p>
                    <p class="product-prijs">€ {{ huidigProduct.prijs }}</p>
                    <button>Leg in Winkelmand</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { producten } from "@/producten.js";

export default {
    data() {
        return {
            huidigProduct: {},
            baseUrl: process.env.BASE_URL
        }
    },
    props: {
        productId: String
    },
    methods: {
        maakAfbeeldingUrl(product) {
            return `${this.baseUrl}producten/${product.categorie}/${product.afbeelding}`;
        }
    },
    created() {
        // Gebruik van unary operator + voor omzetten naar getal, kan ook met Number()
        this.huidigProduct = producten.find(product => product.id === +this.productId);
    }
}
</script>

<style scoped>

.product-container {
    width: 100%;
    display: grid;
    grid-template-columns: repeat(2, minmax(200px, 450px));
    grid-column-gap: 40px;
    justify-content: center;
}

@media screen and (max-width: 640px) {
    .product-container {
        display: block;
    }
}

.terug {
    color: #8FD5B5;
    font-size: 2rem;
    margin-bottom: 3rem;
}

.terug span {
    cursor: pointer;
}

.product-afbeelding {
    text-align: center;
}
.product-afbeelding img {
    max-width: 100%;
}

.product-gegevens {
    background-color: #8FD5B5;
    color: white;
    padding: 2.5rem;
}

.product-titel {
    font-size: 2.5rem;
}

.product-prijs {
    font-weight: bold;
}

.product-gegevens button {
    display: block;
    margin: 0 auto;
    width: 80%;
    padding: 1.5rem;
    background-color: #41B883;
    color: white;
    font-weight: bold;
    border: none;
    cursor: pointer;
}
</style>
