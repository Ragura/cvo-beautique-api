<template>
    <div class="header">
        <h1 class="titel">
            <router-link to="/">Beau-tique</router-link>
        </h1>
        <nav>
            <router-link to="/" exact>Home</router-link>
            <router-link to="/producten">Producten</router-link>
            <router-link to="/over">Over ons</router-link>
            <router-link to="/contact">Contact</router-link>
        </nav>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
a {
    text-decoration: none;
    color: #8FD5B5;
    transition: color 0.4s;
}

a:hover {
    color: white;
}

.titel {
    color: white;
    text-transform: uppercase;
    font-size: 3rem;
}

.header {
    height: 100px;
    background-color: #40B782;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 3em;
    color: white;
}

nav {
    font-size: 2rem;
}

nav a {
    margin: 0 1.5em;
    text-transform: uppercase;
}

a.router-link-active {
    color: white;
}
</style>
