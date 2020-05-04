<template>
  <div>
        <div v-for="element in results" :key="element.id" >
            <br>
            <br>
            <span></span>Numéro: <span>{{ element.id }}</span>
            <br>
            <br>
            <span></span>Catégorie: <span>{{ element.type }}</span>
            <br>
            <br>
            <span></span>Blague: <span>{{ element.setup }}</span>
            <br>
            <br>
            <span></span>Punchline: <span>{{ element.punchline }}</span>
            <br>
            <br>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        name: "Joke",
        data(){
            return{
                results: []
            }
        },
        methods: {
            getMyJoke(){
                axios.get('https://official-joke-api.appspot.com/jokes/programming/ten')
                .then((joke) => {
                    console.log(joke.request.response);
                    this.results = JSON.parse(joke.request.response)
                })
                .catch(() => {
                    this.results = "PAS DE JOKE JE SUIS LA TRISTESSE";
                })
            }
        },
        mounted: function () {
            this.getMyJoke()
        }
    }
</script>

<style>
    .fond{
        background-color: #000000 ;
        background-repeat: no-repeat;
        text-align: left;
        
        
    }
</style>