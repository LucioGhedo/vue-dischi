<template>
  <div id="app">
    <header>
      <PageHeader />
    </header>
    <main>
      <PageContainer />
    </main>
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue';
import PageContainer from './components/PageContainer.vue';


export default {
  name: 'App',
  components: {
    PageHeader,
    PageContainer
}
}
</script>

<style lang="scss">
@import '@/assets/common.scss';
</style>
