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
    <nav class="navbar bg-dark mb-5">
        <div class="container-fluid">
            <a class="navbar-brand text-red fs-3 fw-bold">BOOLFLIX</a>
            <form class="d-flex" role="search">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-danger" type="button">Search</button>
            </form>
        </div>
    </nav>
</template>

<style lang="scss" scoped>
 a {
    color: #E50914;
 }
</style>
