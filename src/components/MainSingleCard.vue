<script>
export default {
    name: 'MainSingleCard',
    props: ['propsCards'],
    data() {
        return {
        }
    },

}
</script>
<template>
    <div class="card m-2">
        <div v-for="(item, index) in propsCards.card_images" :key="index">
            <img :src="item.image_url" alt="">
        </div>
        <!-- <img :src="propsCards.card_images[0].image_url" alt=""> -->

        <h3>{{ propsCards.name }}</h3>
        <h2>{{ propsCards.archetype }}</h2>

    </div>
</template>
<style lang="scss" scoped>
.card {
    width: calc(100% / 6);
    background-color: chocolate;

    div {
        img {
            width: 100%;

        }
    }

    h3 {
        color: #fff;
        text-align: center;
        font-size: 1.6rem;
        padding: 5px;
    }

    h2 {
        text-align: center;
    }
}
</style>