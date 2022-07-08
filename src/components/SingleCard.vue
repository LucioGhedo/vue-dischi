<template>
    <div class="ms_card">
        <img :src="item.image" :alt="item.name">
        <h5>{{item.name}}</h5>
        <p>{{item.species}}</p>
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
    height: 278px;
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
    }
}
</style>