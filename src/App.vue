<script >
import { store } from './store';
import HeaderComp from './components/HeaderComp.vue';
export default {
  name: 'AppVue',
  data() {
    return {
      store,
    }
  },
  components: {
    HeaderComp,
  }
}

</script>

<template>
  <HeaderComp></HeaderComp>
</template>

<style lang="scss">
@use '../src/style/main.scss';
</style>
