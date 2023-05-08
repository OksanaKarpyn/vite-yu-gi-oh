<script>
import MainSingleCard from './MainSingleCard.vue';
import SelectSearch from './SelectSearch.vue';
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
        SelectSearch,
    }
}
</script>
<template>
    <div class="main py-3">
        <div class="container">
            <!-- <SelectSearch @emitsearch="api"></SelectSearch> -->
            <div class="bg-white">
                <div class="count px-5">
                    <p class="mb-0">Found{{ store.arrayCards.length }} cards</p>
                </div>
                <div class="bg-white px-5 cards">
                    <MainSingleCard v-for="(item, index) in store.arrayCards" :key="index" :propsCards='item'>
                    </MainSingleCard>
                    <!--  creo/promps=propsCards -->
                </div>
            </div>


        </div>
    </div>
</template>
<style lang="scss" scoped>
.main {
    background-color: chocolate;


    .count {
        background-color: black;
        padding: 10px;

        p {
            font-size: 1rem;
            color: #fff
        }
    }

    .cards {

        display: flex;
        flex-wrap: wrap;
        background-color: chocolate;
        justify-content: space-between;
    }
}
</style>