<script>
import search from './components/search.vue'
import card from './components/card.vue'
import { state } from './state'
import axios from 'axios'
export default {
    components: { search, card },
    data(){
        return{
            state,
        }
    },
    methods:{
        requestApimovie(typeOfMedia, serced){
            axios
            .get('https://api.themoviedb.org/3/search/' + typeOfMedia + '?query=' + serced)
            .then(renspose => this.state.listMovie = renspose.data.results );
        },
        requestApitv(typeOfMedia, serced){
            axios
            .get('https://api.themoviedb.org/3/search/' + typeOfMedia,{
            params: {
                api_key:'f00ef07e6879a692f570a5453286d6a3',
                query: serced
            }})
            .then(renspose => this.state.listTv = renspose.data.results );
        },
        getAllRequest(){
            this.requestApimovie('movie', this.state.searchKey);
            // this.requestApitv('tv')
            console.log(this.state.listMovie)
        }
    },

    
}
</script>

<template>
    <header>
       <h1>BOOLFLIX</h1>
        <search
        @serchevent="requestApimovie('movie', state.searchKey)" />
   </header>
   <main>
        <h2>MOVIE</h2>
        <card 
        v-for="movie in state.listMovie"
        :key="movie.id"/>
        <h2>SERIES</h2>

   </main>
</template>

<style lang="scss">
@use './assets/styles/general.scss' as *;
header{
    background-color: black;
    display: flex;
    padding: 2rem;
    justify-content: space-between;
    h1{
        color: red;
    }
}
main{
    background-color: rgb(32, 32, 32);
    padding: 3rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    color: white;
}
    
</style>