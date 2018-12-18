<template>
    <div class="product-details">
        <div class="product-container">
            <div class="product-afbeelding">
                <img :src="maakAfbeeldingUrl(huidigProduct)" :alt="huidigProduct.naam">
            </div>
            <div class="product-gegevens">
                <h2 class="product-titel">{{ huidigProduct.naam }}</h2>
                <p class="product-beschrijving">{{ huidigProduct.beschrijving }}</p>
                <p class="product-prijs">€ {{ huidigProduct.prijs }}</p>
                <button>Leg in Winkelmand</button>
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
.product-details {
    display: flex;
    justify-content: center;
}

.product-container {
    max-width: 1180px;
    width: 1000px;
}

.product-afbeelding {
    display: inline-block;
    width: 55%;
    margin-right: 10%;
}
.product-afbeelding img {
    max-width: 100%;
}

.product-gegevens {
    display: inline-block;
    width: 35%;
    background-color: #8FD5B5;
    color: white;
    vertical-align: top;
    padding: 2.5rem;
}

.product-titel {
    font-size: 2.5rem;
}

.product-beschrijving {

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
