<script>
import { store } from '../store.js';
import HeaderSearch from './HeaderSearch.vue';

export default {
    data() {
        return {

        }
    },
    components: {
        HeaderSearch
    },
    methods: {
        getMovie(film) {
            console.log(film)
            this.$emit('selectedFilm', film )
        },

        getSeries(tvSeries) {
            console.log(tvSeries)
            this.$emit('selectedFilm', tvSeries )
        },
    }
}
</script>

<template>
    <nav class="navbar bg-dark mb-5">
        <div class="container-fluid">
            <a class="navbar-brand text-red fs-3 fw-bold">BOOLFLIX</a>
            <HeaderSearch @searchMovie="getMovie" @searchSeries="getSeries"/>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
 a {
    color: #E50914;
 }
</style>