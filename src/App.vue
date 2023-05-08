<script >
import { store } from './store';
import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue';
import SelectSearch from './components/SelectSearch.vue';
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
    SelectSearch,
    MainContentCards,
  },
  created() {
    this.api()
  },
  methods: {
    api() {
      // axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=120&offset=0')
      //   .then((res) => {
      //     console.log(res.data.data)
      //     const oggetti = res.data.data;
      //     this.store.arrayCards = oggetti
      //   })

      if (store.searchValue !== '') {
        axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.searchValue}`)
          .then((res) => {
            console.log(res.data.data)
            const oggetti = res.data.data;
            this.store.arrayCards = oggetti

          })
      } else {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=120&offset=0')
          .then((res) => {
            // console.log(res.data.data)
            const oggetti = res.data.data;
            this.store.arrayCards = oggetti
          })
      }

    }
  }


}

</script>

<template>
  <HeaderComp></HeaderComp>
  <SelectSearch @emitsearch="api"></SelectSearch>

  <MainContentCards>
  </MainContentCards>
</template>

<style lang="scss">
@use '../src/style/main.scss';
</style>
