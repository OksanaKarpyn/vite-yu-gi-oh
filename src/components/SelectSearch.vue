<script>
import { store } from '../store';
export default {
    name: 'MainComp',
    data() {
        return {
            store
        }

    },
    components: {

    }

}
</script>
<template>
    <div>
        <div class="container">
            <select name="" id="" class="form-select input" v-model="store.searchValue" placeholder="search"
                @click.prevent="$emit('emitsearch')">
                <option value="Alien">Alien</option>
                <option value="Noble Knight">Noble Knight</option>
                <option value="@Ignister">@Ignister</option>
                <option value="Unchained">Unchained</option>
                <option value="Abyss Actor">Abyss Actor</option>
                <option value="Mermail">Mermail</option>
                <option value="Adamancipator">Adamancipator</option>
                <option value="Melodius">Melodius</option>
                <option value="ABC">ABC</option>
            </select>
        </div>
    </div>
</template>
<style lang="scss" scoped>
div {
    background-color: chocolate;

    .container {
        padding-top: 20px;

        .input {
            width: 200px;
            padding: 15px;
        }
    }
}
</style>