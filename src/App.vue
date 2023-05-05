<script >
import { store } from './store';
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';
import MainContentCards from './components/MainContentCards.vue';
export default {
  name: 'AppVue',
  data() {
    return {
      store,
    }
  },
  components: {
    HeaderComp,
    MainComp,
    MainContentCards,
  },
  created() {
    this.api()
  },
  methods: {
    api() {

      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=3')
        .then((res) => {
          console.log(res.data.data)
          const oggetti = res.data.data;
          this.store.arrayCards = oggetti
        })

    }
  }


}

</script>

<template>
  <HeaderComp></HeaderComp>
  <MainComp></MainComp>
  <MainContentCards></MainContentCards>
</template>

<style lang="scss">
@use '../src/style/main.scss';
</style>
