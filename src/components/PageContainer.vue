<template>
    <div class="back">
        <div class="container">
            <div class="row">
                <div class="col-12 d-flex justify-content-between flex-wrap">
                    <div v-for="item, index in dataList" :key="index">
                        <SingleCard :info="dataList" :item="item" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import SingleCard from './SingleCard.vue';


export default {
    name: "PageContainer",
    data() {
        return {
            url: "https://rickandmortyapi.com/api/character",
            dataList: [],
        };
    },
    created() {
        this.getData();
    },
    methods: {
        getData() {
            axios.get(this.url).then((result) => {
                this.dataList = result.data.results;
            });
        }
    },
    components: { SingleCard }
}
</script>

<style lang="scss" scoped>
@import '../assets/common.scss';
.back {
    background-color: $main-color;
    color: white;
}
</style>