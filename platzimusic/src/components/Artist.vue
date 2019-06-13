

<template lang="html">
    <li>
        <h2>
            <a v-bind:href="artist.url" target="_blank">{{ artist.name }}</a>
            <img v-bind:src="artist.image[2]['#text']" >
        </h2>
    </li>
</template>


<script>
export default {
    name: 'artist',
    props: ['artist']
};
</script>

<style>
    li{
        display: block;
        margin: 10px 0px;
    }
</style>


