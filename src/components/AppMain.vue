<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store,
            posterMediaUrl: 'https://image.tmdb.org/t/p/w342/'
        }
    },
}
</script>

<template>
    <div class="container">

        <!-- ! FILM SECTION -->
        <section>

            <h2 v-show="store.moviesList.length === 0" class="text-white">Cerca Film o Serie TV!</h2>

            <div v-show="store.moviesList.length !== 0">
                <h2 class="text-white">FILMS</h2>
                <h5 class="mb-4 text-white">Risultati trovati: {{ store.moviesList.length }}</h5>
            </div>

            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3">
                <div class="col text-white text-center g-5 position-relative" v-for="movie in store.moviesList" :key="movie.id">

                    <div>
                        <img :src="posterMediaUrl+movie.poster_path" alt="movie-poster" class="poster">
                    </div>

                    <ul class="p-0 position-absolute">
                        <li>
                            <b>Titolo:</b> {{ movie.title }}
                        </li>
                        <li>
                            <b>Titolo originale:</b> {{ movie.original_title }}
                        </li>

                        <!-- USO V-IF PER CAPIRE QUALE BANDIERA METTERE IN movie.original_lenguage -->
                        <li v-if="movie.original_language === 'en'">
                            <b>Lingua originale:</b> <img src="../assets/img/united-kingdom.png" alt="uk_flag" class="flag">
                        </li>
                        <li v-else-if="movie.original_language === 'ja'">
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

                        <!-- USO V-IF PER CAPIRE QUANTE STELLE ASSEGNARE COME MEDIA DEI VOTI -->
                        <li v-if="movie.vote_average >= 8">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="movie.vote_average >= 6">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="movie.vote_average >= 4">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="movie.vote_average >= 2">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="movie.vote_average < 2">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;</span>
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- ! TV SERIES SECTION -->
        <section>
            <div v-show="store.tvSeriesList.length !== 0">
                <hr class="text-white mt-5">
                <h2 class="text-white mt-5">SERIE TV</h2>
                <h5 class="mb-4 text-white">Risultati trovati: {{ store.tvSeriesList.length }}</h5>
            </div>
            
            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3">
                <div class="col text-white text-center g-5 position-relative" v-for="serie in store.tvSeriesList" :key="serie.id">

                    <div>
                        <img :src="posterMediaUrl+serie.poster_path" alt="tv-series-poster" class="poster">
                    </div>

                    <ul class="p-0 position-absolute">
                        <li>
                            <b>Titolo:</b> {{ serie.name }}
                        </li>
                        <li>
                            <b>Titolo originale:</b> {{ serie.original_name }}
                        </li>

                        <!-- USO V-IF PER CAPIRE QUALE BANDIERA METTERE IN serie.original_lenguage -->
                        <li v-if="serie.original_language === 'en'">
                            <b>Lingua originale:</b> <img src="../assets/img/united-kingdom.png" alt="uk_flag" class="flag">
                        </li>
                        <li v-else-if="serie.original_language === 'ja'">
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

                        <!-- USO V-IF PER CAPIRE QUANTE STELLE ASSEGNARE COME MEDIA DEI VOTI -->
                        <li v-if="serie.vote_average >= 8">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;&#9733;&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="serie.vote_average >= 6">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="serie.vote_average >= 4">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="serie.vote_average >= 2">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;&#9733;</span>
                        </li>
                        <li v-else-if="serie.vote_average < 2">
                            <b>Media dei voti:</b> <span class="vote-stars">&#9733;</span>
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

        img.poster {
            max-width: 100%;
            border-radius: 10px;            
        }

        ul {
            display: none;
            list-style-type: none;
            max-width: 70%;
            top: 35%;
            left: 15%;
            right: 0;
            text-shadow: 0 0 5px black;

            img.flag {
                display: inline;
                height: 25px;
                margin-left: 10px;
            };

            .vote-stars {
                color: rgb(255, 230, 0);
            }
        }
    }

    div.col:hover {
        img.poster {
            filter: blur(5px) grayscale(80%);
        }

        ul {
            display: inline;
        }
    }
</style>