<template>
<div style="container mx-auto">
<Que 
title ="問題" 
v-bind:que ="mondai"
/>
<Ans v-bind:ans ="kotae.A" />
<Ans v-bind:ans ="kotae.B" />
<Ans v-bind:ans ="kotae.C" />
<Ans v-bind:ans ="kotae.D" />
</div>
</template>

<script>
import Que from './components/Que.vue';
import Ans from './components/Ans.vue';

export default {
    name:'App',
    components: {
        Que,
        Ans,
    },
    data() {
        return {
            mondai:"光の三原色に当てはまらないものは？",
            kotae:{
                A:"BLUE",
                B:"RED",
                C:"WHITE",
                D:"GREEN"
                }
        }
    }
}
</script>