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
        getMovie(info) {
            console.log(info)
            this.$emit('selectedFilm', info )
        },
    }
}
</script>

<template>
    <nav class="navbar bg-dark mb-5">
        <div class="container-fluid">
            <a class="navbar-brand text-red fs-3 fw-bold">BOOLFLIX</a>
            <HeaderSearch @search="getMovie"/>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
 a {
    color: #E50914;
 }
</style>