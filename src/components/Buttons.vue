<template>
<div class="buttMain">
    <button @click="$emit('saveList')" class="save">Save</button>
    <button @click="$emit('clearList')" class="clear">Clear</button>
</div>
</template>

<script>
export default {
    name: 'Buttons',
    props: [],
}
</script>

<style>

.buttMain {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    justify-content: center;
    padding: 10px 0;
}

.buttMain > button {
    margin: 0 5px;
    border-radius: 7px;
    padding: 10px;
    border: none;
    box-shadow:4px 4px 10px rgba(0,0,0,0.26);
    width:60px;
    height: 35px;
    transition:  .3s ease;
    width: 130px;
}

.buttMain > button:hover {
    border-radius: 7px;
    padding: 10px;
    border: none;
    border: 0,5px solid black;
    box-shadow:6px 6px 12px rgba(255,255,255,0.36);
}


.buttMain > button:active {
    box-sizing: border-box;
   border: 1px solid rgba(128,128,128, 0.4);
}

</style>