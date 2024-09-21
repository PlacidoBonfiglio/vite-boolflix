<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store.js';

    export default {
        data() {
            return {

            }
        },
        components: {
            AppHeader,
            AppMain
        }
    }

</script>

<template>
    <AppHeader/>
    <AppMain/>
</template>

<style lang="scss">
@use 'bootstrap/scss/bootstrap.scss';
@use './styles/general.scss' as *;
</style>