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

        <h2 class="mb-4 text-white">FILM</h2>

        <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3">
            <div class="col text-white text-center g-5" v-for="(movie, index) in store.moviesList" :key="index">
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

        <h2 class="mb-4 text-white">SERIE TV</h2>

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
</template>

<style lang="scss" scoped>
    div.col {
        min-height: 400px;
        cursor: pointer;

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