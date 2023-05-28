<script>
import { state } from '../state'
export default {
    data(){
        return{
            state,
            searchString:'',
        }
    },
    methods:{
        geteventserch(){
            this.$emit('serchevent');
            this.state.searchKey = this.searchString;
            console.log(this.state.searchKey)
        }
        
    }
    
}
</script>
<template>
    <div class="container">
        <input type="text"
        v-model="searchString"
        @keyup.enter="geteventserch">
        <button
        @click="geteventserch">CERCA</button>
    </div>
</template>

<style lang="scss">
    .container{
        display: flex;
        gap: 1rem;
        align-items: center;
    }
</style>