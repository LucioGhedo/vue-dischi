<template>
    <div class="back">
        <div class="container">
            <div class="row">
                <div class="col-12 d-flex justify-content-evenly flex-wrap">
                    <div v-if="isLoadin">
                        <div class="ripple-loader">
                            <div></div>
                            <div></div>
                        </div>
                        <h2>LOADING CONTENT</h2>
                    </div>
                    <div v-else>
                        <div>
                            <SearchBar @select="selectCategory" />
                        </div>
                        <div class="container">
                            <div class="row">
                                <div class="d-flex flex-wrap">
                                    <div v-for="item, index in filteredDataList" :key="index">
                                        <SingleCard :info="dataList" :item="item" />
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import SingleCard from './SingleCard.vue';
import SearchBar from './SearchBar.vue';


export default {
    name: "PageContainer",
    data() {
        return {
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            dataList: [],
            isLoadin: true,
            filteredDataList: [],
        };
    },
    created() {
        this.getData();
    },
    methods: {
        getData() {
            axios.get(this.url).then((result) => {
                this.dataList = result.data.response;
                setTimeout(() => {
                    this.isLoadin = false;
                    this.filteredDataList = this.dataList
                }, 1000);
            });
        },
        selectCategory(select) {
        this.filteredDataList = [];
        for(let i = 0; i < this.dataList.length; i++) {
            if (this.dataList[i].genre.toLowerCase() == select) {
                this.filteredDataList.push(this.dataList[i]);
            } 
        }
        this.selectAll(select)
        },
        selectAll(select) {
            if (select == 'all') {
                this.filteredDataList = this.dataList;
            }
        }
    
    },
    components: { SingleCard, SearchBar }
}
</script>

<style lang="scss" scoped>
@import '../assets/common.scss';
.back {
    background-color: $main-color;
    color: white;
}
h2 {
    font-size: 80px;
    color: white;
}
</style>