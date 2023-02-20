<template>
    <div class="row">
        <Pixel v-for="n in 40"></Pixel>
    </div>
</template>

<style scoped>

.row {
    display: flex;
    flex-direction: row;
}

</style>

<script lang="ts">

import Pixel from './Pixel.vue';

export default {
    components: {
        Pixel
    },
    data() {
        return {

        }
    }
}

</script>