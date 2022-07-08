<template>
    <div class="back">
        <img src="../assets/spoti.png" alt="spotify">
    </div>
</template>

<script>
export default {
    name:'PageHeader',
}
</script>

<style lang="scss" scoped>
@import '../assets/common.scss';

.back {
    background-color: $primary;
    color: white
}
img {
    width: 90px;
    padding: 15px;
}
</style>