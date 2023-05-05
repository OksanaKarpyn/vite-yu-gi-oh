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
    <div class="card">
        <div v-for="(item, index) in propsCards.card_images" :key="index">
            <img :src="item.image_url" alt="">
        </div>
        <h3>{{ propsCards.name }}</h3>
        <h2>{{ propsCards.archetype }}</h2>

    </div>
</template>
<style lang="scss" scoped></style>