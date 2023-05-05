<script>
import MainSingleCard from './MainSingleCard.vue';
import { store } from '../store';
export default {
    name: 'MainContentCards',
    data() {
        return {
            store,
        }
    },
    components: {
        MainSingleCard,
    }
}
</script>
<template>
    <MainSingleCard v-for="(item, index) in store.arrayCards" :key="index" :propsCards='item'></MainSingleCard>
    <!--  creo/promps=propsCards -->
</template>
<style></style>