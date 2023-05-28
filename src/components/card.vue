<script>
import {state} from '../state.js'
export default {
    data(){
        return{
            state,
        }
    }
}
</script>
<template>
   <div class="card-container">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTvDFGc_6Z6y4cG_E9559Kx7O-6l6SPeD4s1w&usqp=CAU" alt="">
        <div class="info-card">
            <h5>{{ movie.title }}</h5>
            <h4>{{ movie.original_title }}</h4>
            <p class="lang">it</p>
            <p class="description">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia quam iure aliquid sit facilis illo saepe aspernatur odit ad inventore </p>
        </div>
   </div>
</template>

<style lang="scss">
@use '../assets/styles/general.scss' as *;
    .card-container{
        position: relative;
        width: 30%;
        img{
            width: 100%;
        }
        .info-card{
            width: 100%;
            position: absolute;
            top: 10px;
            text-align: center;
            overflow: auto;
        }
    }
</style>