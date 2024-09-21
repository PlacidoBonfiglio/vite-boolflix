<script>
import { store } from '../store.js';
import MainSearch from './MainSearch.vue';

export default {
    data() {
        return {

        }
    },
    components: {
        MainSearch
    }
}
</script>

<template>
    <nav class="navbar bg-dark mb-5">
        <div class="container-fluid">
            <a class="navbar-brand text-red fs-3 fw-bold">BOOLFLIX</a>
            <MainSearch/>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
 a {
    color: #E50914;
 }
</style>