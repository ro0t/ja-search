<template>
    <div id="tab-examples">
        <div>
            <v-search />
        </div>
    </div>
</template>

<script lang="ts">
import Search from './components/Search';
import Search2 from './components/Search2';
import Search3 from './components/Search3';
import Search4 from './components/Search4';

export default {
    components: {
        'v-search': Search,
        'v-search2': Search2,
        'v-search3': Search3,
        'v-search4': Search4,
    }
}
</script>

<style lang="scss" scoped>
    #tab-examples {
        > div:not(:last-child) {
            margin-bottom: 24px;
        }
    }
</style>