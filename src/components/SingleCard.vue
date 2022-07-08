<template>
    <div class="ms_card">
        <img :src="item.poster" :alt="item.title">
        <div class="text-center">
            <h5>{{item.title}}</h5>
            <p>{{item.author}}</p>
            <p>{{item.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SingleCard',
    props: {
        info: Array,
        item: Object,
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/common.scss';
.ms_card {
    width: 150px;
    height: 300px;
    padding: 15px;
    background-color: $primary;
    border: none;
    margin: 15px;
    color: white;
    img {
        width: 122px;
        margin-bottom: 15px;
    }
    p {
        color: grey;
        display: block;
    }
}
</style>