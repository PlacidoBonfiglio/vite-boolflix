<script>
import { store } from '../store.js';
import axios from 'axios';

export default {
    data() {
        return {
            store,
            posterMoviesSrc: 'https://image.tmdb.org/t/p/w342/'
        }
    },
    methods: {
        getPosterPic() {
            console.log('POSTER!')
            axios.get(this.posterMoviesSrc, {
                params: {
                    poster_path: store.moviesList.poster_path
                }
            })
        },
    },
}
</script>

<template>
    <div class="container">

        <!-- ! FILM SECTION -->
        <section>
            <h2 v-show="store.moviesList.length !== 0" class="text-white">FILMS</h2>
            <h5 v-show="store.moviesList.length !== 0" class="mb-4 text-white">Risultati trovati: {{ store.moviesList.length }}</h5>

            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3">
                <div class="col text-white text-center g-5" v-for="(movie, index) in store.moviesList" :key="index">

                    <div>
                        <img :src="getPosterPic[index]" alt="movie poster">
                    </div>

                    <ul class="p-0">
                        <li>
                            <b>Titolo:</b> {{ movie.title }}
                        </li>
                        <li>
                            <b>Titolo originale:</b> {{ movie.original_title }}
                        </li>
                        <li v-if="movie.original_language === 'en'">
                            <b>Lingua originale:</b> <img src="../assets/img/united-kingdom.png" alt="uk_flag" class="flag">
                        </li>
                        <li v-if="movie.original_language === 'ja'">
                            <b>Lingua originale:</b> <img src="../assets/img/japan.png" alt="ja_flag" class="flag">
                        </li>
                        <li v-else-if="movie.original_language === 'it'">
                            <b>Lingua originale:</b> <img src="../assets/img/92144_italy_icon.png" alt="it_flag" class="flag">
                        </li>
                        <li v-else-if="movie.original_language === 'fr'">
                            <b>Lingua originale:</b> <img src="../assets/img/92086_france_icon.png" alt="fr_flag" class="flag">
                        </li>
                        <li v-else-if="movie.original_language === 'es'">
                            <b>Lingua originale:</b> <img src="../assets/img/spain.png" alt="es_flag" class="flag">
                        </li>
                        <li v-else-if="movie.original_language === 'de'">
                            <b>Lingua originale:</b> <img src="../assets/img/92094_germany_icon.png" alt="de_flag" class="flag">
                        </li>
                        <li>
                            <b>Media dei voti:</b> {{ movie.vote_average }}
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- ! TV SERIES SECTION -->
        <section>
            <h2 v-show="store.tvSeriesList.length !== 0" class="text-white">SERIE TV</h2>
            <h5 v-show="store.tvSeriesList.length !== 0" class="mb-4 text-white">Risultati trovati: {{ store.tvSeriesList.length }}</h5>

            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3">
                <div class="col text-white text-center g-5" v-for="(serie, index) in store.tvSeriesList" :key="index">
                    <ul class="p-0">
                        <li>
                            <b>Titolo:</b> {{ serie.name }}
                        </li>
                        <li>
                            <b>Titolo originale:</b> {{ serie.original_name }}
                        </li>
                        <li v-if="serie.original_language === 'en'">
                            <b>Lingua originale:</b> <img src="../assets/img/united-kingdom.png" alt="uk_flag" class="flag">
                        </li>
                        <li v-if="serie.original_language === 'ja'">
                            <b>Lingua originale:</b> <img src="../assets/img/japan.png" alt="ja_flag" class="flag">
                        </li>
                        <li v-else-if="serie.original_language === 'it'">
                            <b>Lingua originale:</b> <img src="../assets/img/92144_italy_icon.png" alt="it_flag" class="flag">
                        </li>
                        <li v-else-if="serie.original_language === 'fr'">
                            <b>Lingua originale:</b> <img src="../assets/img/92086_france_icon.png" alt="fr_flag" class="flag">
                        </li>
                        <li v-else-if="serie.original_language === 'es'">
                            <b>Lingua originale:</b> <img src="../assets/img/spain.png" alt="es_flag" class="flag">
                        </li>
                        <li v-else-if="serie.original_language === 'de'">
                            <b>Lingua originale:</b> <img src="../assets/img/92094_germany_icon.png" alt="de_flag" class="flag">
                        </li>
                        <li>
                            <b>Media dei voti:</b> {{ serie.vote_average }}
                        </li>
                    </ul>
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
    div.col {
        min-height: 400px;
        cursor: pointer;

        img {
            max-width: 100%;
        }

        ul {
            list-style-type: none;

            img.flag {
                display: inline;
                height: 25px;
                margin-left: 10px;
            };
        }
    }
</style>