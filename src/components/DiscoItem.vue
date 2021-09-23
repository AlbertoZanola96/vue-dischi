<template>
    <div class="container">
        <img :src="item.poster" :alt="item.img">
        <h4>{{item.title.toUpperCase()}}</h4>
        <h5>{{item.author}}</h5>
        <h5>{{item.year}}</h5>
    </div>
</template>

<script>
export default {
    name: 'discoItem',
    props: ['item']
}
</script>

<style scoped lang="scss">
    .container {
        width: 100%;
        cursor: pointer;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        flex-direction: column;
        min-height: 300px;



        img {
            width: 150px;
            height: 50%;
        }

        h4 {
            margin: 6px 0 4px 0;
            color: white;
        }
        h5 {
            color: #64797F;
        }

        
    }
</style>