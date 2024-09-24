<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store
        }
    },
    methods: {
        mediaRequest() {
            this.$emit('searchMovie', store.inputResult)
            this.$emit('searchTvSeries', store.inputResult)
        },
    }
}
</script>

<template>
    <div class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Cerca" aria-label="Search" @keyup.enter="mediaRequest" v-model.trim="store.inputResult">
        <button class="btn btn-danger" type="button" @click="mediaRequest">Cerca</button>
    </div>
</template>

<style lang="scss" scoped>
</style>