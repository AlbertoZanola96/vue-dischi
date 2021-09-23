<template>
    <div>
        <div class="container">
            <section>

            </section>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'DiscList',
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
                    this.listaDischi = risposta.data;
                })
        }
    }
}
</script>

<style scoped lang="scss">
    .container{
        width: 100%;
        height: calc(100vh - 100px);
        background-color: #1E2D3B;
    }

</style>