<script setup>
const props=defineProps({color:String,link:String,text:String,hover:String,newline:Boolean})
</script>
<template>
    <a class="griditem" :href="link || ''" :style="newline?'grid-area:auto/1;':''">
        <div :class="color"><p>{{text || ''}}</p></div>
        <p>{{hover || ''}}</p>
    </a>
</template>
<style scoped>
a.griditem{
    position:relative;
    display:flex;
    align-items:center;
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
a.griditem div{
    background:#f0f0f0;
    transition:.5s;
    display:flex;
    border-radius:3px;
    width:280px;
    height:90px;
    padding:5px 10px;
}
a.griditem:hover div{
    opacity:0.3;
    width:290px;
    height:100px;
    margin:-5px;
    filter:blur(5px)
}
a.griditem div p{
    align-self:center;
    opacity:1;
    transition:none;
    position:absolute;
    text-align:left;
    margin:auto;
    padding:5%;
    overflow-wrap:anywhere;
    font-size:1em;
    letter-spacing:0;
}
</style>