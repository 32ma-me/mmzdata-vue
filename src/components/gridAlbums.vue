<script setup>
const props=defineProps({link:String,text:String,image:String})
function imagePath(){return require(image.value)}
</script>
<template>
    <a class="griditem" :href="link || ''">
        <img :src="image">
        <p>{{text || ''}}</p>
    </a>
</template>
<style scoped>
a.griditem{
    position:relative;
    display:flex;
    align-items:center;
}
a.griditem img{
    transition:.5s;
    width:300px;
    height:300px;
}
a.griditem:hover img{
    opacity:0.3;
    filter:blur(5px);
    width:310px;
    height:310px;
    margin:-5px;
}
a.griditem p{
    opacity:0;
    transition:.5s;
    position:absolute;
    left:50%;
    transform:translateX(-50%);
    text-align:center;
    margin:auto;
    width:90%;
    overflow-wrap:anywhere;
    font-size:0.9em;
    letter-spacing:1.5px;
}
a.griditem:hover p{
    font-size:1em;
    letter-spacing:0;
    opacity:1;
}
</style>