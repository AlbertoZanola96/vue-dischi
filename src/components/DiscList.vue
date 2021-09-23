<template>
    <div class="container">
        <div class="x" v-for="(disco, index) in listaDischi" :key="index">
            <DiscoItem :item="disco" />
        </div>
    </div>
    
</template>

<script>
import axios from 'axios';
import DiscoItem from "../components/DiscoItem.vue";

export default {
    name: 'DiscList',
    components: {
        DiscoItem
    },
    data() {
        return {
            url: 'https://flynn.boolean.careers/exercises/api/array/music',
            listaDischi: []
        }
    }, 
    created() {
        this.dischi();
    },
    methods: {
        dischi() {
            axios
                .get(this.url)
                .then(risposta => {
                    console.log(risposta.data.response)
                    this.listaDischi = risposta.data.response;
                })
        }
    }
}
</script>

<style scoped lang="scss">
    .container{
        width: 100%;
        height: 100%;
        background-color: #1E2D3B;
        display: flex;
        justify-content: flex-start;
        flex-wrap: wrap;
; 
               
        .x {
            margin: 70px auto;
            padding: 0 80px 0 80px;
        }
    }
</style>