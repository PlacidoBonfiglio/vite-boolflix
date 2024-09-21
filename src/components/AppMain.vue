<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            apiUrl: 'https://api.themoviedb.org/3/search/movie/'
        }
    },
    methods: {
        getMovies() {
            axios.get(this.apiUrl, {
                params: {
                    api_key: '8886119bc2762c257900fe2ce351380f',
                    query: ''
                }
            }) 
            .then((response) => {
                console.log(response);
            })
            .catch(function (error) {
                console.log(error);
            });
        },
    }
}
</script>

<template>
    <section class="container">
        <div class="row row-cols-3">
            <div class="col text-white text-center">
                ciao
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    div.row {
        height: 400px;
    }
</style>