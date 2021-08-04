<template>
    <div>
        <SearchJokes v-on:search-text="searchText"/>
        <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.leadId"/>
    </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue';
import SearchJokes from '../../components/SearchJokes.vue';

export default {
    components: {
        Joke,
        SearchJokes
    },
    data() {
        return {
            jokes: []
        }
    },
    async created(){
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {

            const res = await axios.get('https://icanhazdadjoke.com/search', config);
            this.jokes = res.data.results;
            // const res = await axios.get('http://localhost:3100/transaction/v1/transaction', config);
            // this.jokes = res.data.data;
            // console.log(this.jokes);
        } catch (err) {
            console.log(err);
        }
    },
    methods: {
        async searchText(text){
            const config = {
                headers: {
                    'Accept': 'application/json'
                }
            }

            try {
                const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
                this.jokes = res.data.results;
                // const res = await axios.get(`http://localhost:3100/transaction/v1/transaction/?id=${text}`, config);
                // this.jokes = res.data.data;
                // console.log(text);
                // console.log(this.jokes);
            } catch (err) {
                console.log(err);
            }
        }
    },
    head() {
        return {
            title: 'Dad Jokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dad jokes',
                }
            ]
        }
    }
}
</script>