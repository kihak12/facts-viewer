<template>
    <div class="container">
        <div class="content">
            <div v-if="!fetched">Chargement...</div>
            <div v-else>
                <span>{{ translate }}</span>
            </div>
            <div class="btn-container">
                <button v-bind:onclick="getRandomFact">Refresh</button>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: "fact-component",
    data() {
        return {
            fetched: false,
            fact: "",
            translate: "",
        }
    },
    methods: {
        getRandomFact() {
            this.fetched = false;
            let apiKeyFact = "";
            let headers = {
                'X-Api-Key': apiKeyFact
            };
            axios
                .get("https://api.api-ninjas.com/v1/facts?limit=1", { headers: headers })
                .then((response) => {
                    this.fact = response.data[0].fact
                    this.translateText(this.fact);
                })
        },
        translateText(text) {
            this.fetched = false;
            let apiKeyDeepl = "";
            let url = `https://api-free.deepl.com/v2/translate?auth_key=${apiKeyDeepl}&target_lang=FR&tag_handling=html&preserve_formatting=true&text=${text}`;
            axios
                .get(url)
                .then((response) => {
                    this.translate = response.data.translations[0].text;
                    this.fetched = true;
                })
        }
    },
    mounted() {
        this.getRandomFact();
    }
}
</script>

<style scoped>
.container {
    height: calc(100vh - 80px);
    display: flex;
    align-items: center;
    justify-content: center;
    align-content: center;
    transform: translateY(-10%);
}

.btn-container {
    margin: 1.5em 0 0 0;
    display: flex;
    align-items: center;
    justify-content: center;
    align-content: center;
}

button {
    position: relative;
    cursor: pointer;
    padding: 1em 2em;
    background-color: white;
    border: none;
    box-shadow: #0000001f 5px 5px 10px;
    transition: all .5s ease;
    color: black;
}

button::before {
    content: '';
    background-color: rgba(0, 0, 0, 10%);
    position: absolute;
    left: 0;
    top: 0;
    transition: all .5s ease;
    height: 100%;
    width: 0%;
}

button:hover::before {
    width: 100%;
}

.content {
    max-width: 80%;
}

span {
    color: black;
}
</style>