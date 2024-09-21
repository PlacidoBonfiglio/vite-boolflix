<script>
import { store } from '../store.js';

export default {
    data() {
        return {

        }
    },
}
</script>

<template>
    <form class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" @keyup.enter="">
        <button class="btn btn-danger" type="button">Search</button>
    </form>
</template>

<style lang="scss" scoped>

</style>