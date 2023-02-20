<template>
    <div class="pixel" ref="pixel" @click="changeColor()"></div>
</template>

<style scoped>

div {
    width: 1rem;
    height: 1rem;
    background-color: black;
    cursor: pointer;
}

div:hover {
    box-shadow:inset 0px 0px 0px 0.1rem white;
}

</style>

<script lang="ts">

export default {
    methods: {
        changeColor() {
            let newclr = localStorage.getItem("selected_color") as string
            (this.$refs.pixel as HTMLDivElement).style.backgroundColor = newclr
        }
    }
}

</script>