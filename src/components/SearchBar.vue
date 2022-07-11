<template>
  <div>
    <div class="container">
        <div class="text-center">
            <select @change="$emit('search', selectCategory($event))" name="search" id="search" value="all">
                <option value="all">All</option>
                <option value="rock">Rock</option>
                <option value="pop">Pop</option>
                <option value="jazz">Jazz</option>
                <option value="metal">Metal</option>
            </select>
        </div>    
    </div>
  </div>  
</template>

<script>
export default {
    name: 'SearchBar',
    data() {
        return {
            categoryId: '',
        }
    },
    methods: {
        selectCategory(event) {
        this.categoryId = event.target.value
        this.$emit('select', this.categoryId)
    }
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/common.scss';
div {
    background-color: $main-color;
}

</style>