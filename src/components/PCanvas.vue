<template>
    <div class="canvas">
        <Pixelrow v-for="m in 40"></Pixelrow>
    </div>
</template>

<style scoped>

div {
    display: flex;
    flex-direction: column;
}

</style>

<script lang="ts">

import Pixelrow from './Pixelrow.vue';

export default {
    components: {
        Pixelrow
    }
}

</script>