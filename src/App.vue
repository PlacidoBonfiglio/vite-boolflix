<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store.js';

    export default {
      data() {
          return {
            moviesUrl: 'https://api.themoviedb.org/3/search/movie',
            tvSeriesUrl: 'https://api.themoviedb.org/3/search/tv',
            store
          }
      },
      components: {
          AppHeader,
          AppMain
      },
      methods: {

        // CHIAMATA API MOVIES
        getMovies( moviesResult = null ) {
            console.log('MOVIES!')
            axios.get(this.moviesUrl, {
                params: {
                    api_key: '8886119bc2762c257900fe2ce351380f',
                    language: 'it_IT',
                    query: moviesResult
                }
            }) 
            .then((response) => {
                console.log(response.data.results);
                store.moviesList = response.data.results
            })
            .catch(function (error) {
                console.log(error);
            });
        },
    },
    }

</script>

<template>
    <AppHeader @selectedFilm="getMovies"/>
    <AppMain/>
</template>

<style lang="scss">
@use 'bootstrap/scss/bootstrap.scss';
@use './styles/general.scss' as *;
</style>