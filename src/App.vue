<template>
    <div id="colsel">
        <span>
            Current Colour: <span ref="coldisplay" id="curcol">#000000</span><br>
            <input type="color" name="" id="colorselect">
        </span>
    </div>
    <PCanvas class="canvas"></PCanvas><br><br>
    <button onclick="html2canvas(document.getElementsByClassName('canvas')[0]).then(canvas=>{const i = canvas.toDataURL('image/png'); window.open().document.write(`<iframe src=${i} frameborder='0' style='border:0; top:0px; left:0px; bottom:0px; right:0px; width:100%; height:100%;' allowfullscreen></iframe>`);})">Open as PNG</button>
</template>

<style scoped>

#colsec {
    border: 0.2rem solid #00000032;
}

input[type=color]{
	width: 40px;
	height: 40px;
	border: none;
	border-radius: 40px;
	background: none;
}
input[type="color"]::-webkit-color-swatch-wrapper {
	padding: 0;
}
input[type="color"]::-webkit-color-swatch {
	border: solid 1px transparent;
	border-radius: 40px;
}

</style>

<script lang="ts">

import Pixel from './components/Pixel.vue'
import PCanvas from './components/PCanvas.vue'
import Pixelrow from './components/Pixelrow.vue'

export default {
    methods: {
        launchClr() {
            console.log(localStorage.getItem("selected_color"))
        },
    },
    mounted() {
        setInterval(() => {
            localStorage.setItem("selected_color", (document.getElementById("colorselect") as HTMLInputElement).value)
            let val = localStorage.getItem("selected_color") as string
            let coldisplay = this.$refs.coldisplay as HTMLSpanElement
            coldisplay.innerHTML = val
            coldisplay.style.color = val
        }, 20)
    },
    components: {
        Pixel,
        PCanvas,
        Pixelrow
    }
}

</script>