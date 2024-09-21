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
    },
    methods: {
        fammiSapere() {
            console.log('funziono')
        },
    }
}
</script>

<template>
    <nav class="navbar bg-dark mb-5">
        <div class="container-fluid">
            <a class="navbar-brand text-red fs-3 fw-bold">BOOLFLIX</a>
            <MainSearch @search="fammiSapere"/>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
 a {
    color: #E50914;
 }
</style>