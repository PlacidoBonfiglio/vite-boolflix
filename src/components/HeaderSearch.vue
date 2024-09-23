<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store
        }
    },
    methods: {
        sendRequest() {
            this.$emit('search', store.inputResult)
        }
    }
}
</script>

<template>
    <div class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" @keyup.enter="sendRequest" v-model.trim="store.inputResult">
        <button class="btn btn-danger" type="button" @click="sendRequest">Cerca</button>
    </div>
</template>

<style lang="scss" scoped>

</style>