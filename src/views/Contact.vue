<template>
    <main class="contact">
        <h1>Contacteer ons</h1>
        <form @submit.prevent>
            <div class="input-groep">
                <label for="naam">Uw naam:</label>
                <input id="naam" type="text">                
            </div>

            <div class="input-groep">
                <label for="email">Uw emailadres:</label>
                <input id="email" type="email">                
            </div>

            <label for="naam">Uw vraag:</label>
            <textarea id="vraag" rows="10" ></textarea>

            <button>Verzenden</button>          
        </form>
    </main>
</template>

<script>
export default {

}
</script>

<style>

h1 {
    font-size: 8rem;
    color: #41B883;
}

form {
    width: 90%;
    max-width: 800px;
    font-size: 2rem;
    margin-top: 2rem;
    border: 1px solid #41B883;
    padding: 2rem;
    border-radius: 10px;
    display: flex;
    flex-flow: column nowrap;
}

.input-groep {
    display: flex;
    justify-content: center;
    margin-bottom: 2em;
}

.input-groep label {
    width: 40%;
}

.input-groep input {
    flex: 1;
    border-radius: 4px;
    border: 1px solid #41B883;
}

textarea {
    display: block;
    margin-top: 1rem;
    width: 100%;
    resize: none;
}

form button {
    margin-top: 1rem;
    width: 150px;
    background-color: #40B782;
    color: white;
    text-align: center;
    padding: 1rem;
    font-size: 2rem;
    align-self: flex-end;
    cursor: pointer;
}


</style>
