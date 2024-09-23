<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store,
        }
    },
    
}
</script>

<template>
    <section class="container">
        <div class="row row-cols-3">
            <div class="col text-white text-center" v-for="(movie, index) in store.moviesList" :key="index">
                <ul>
                    <li>
                        <b>Titolo:</b> {{ movie.title }}
                    </li>
                    <li>
                        <b>Titolo originale:</b> {{ movie.original_title }}
                    </li>
                    <li>
                        <b>Lingua originale:</b> {{ movie.original_language }}
                    </li>
                    <li>
                        <b>Media dei voti:</b> {{ movie.vote_average }}
                    </li>
                </ul>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    div.row {
        height: 400px;

        ul {
            list-style-type: none;
        }
    }
</style>