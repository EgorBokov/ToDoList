<template>
<div class='main'>
    <input id="inp" v-model="inputValue" placeholder="Enter the task" />
    <button class="mainButt" @click="$emit('addTask', inputValue)">Add</button>
</div>
</template>


<script>
export default {
        name: 'Search',
        props:['todos'],
        data(){
            return {
                inputValue: '',
            }
    },
}


</script>

<style>

input { 
    border-radius: 20px;
    padding: 10px;
    border: none;
    box-shadow:4px 4px 10px rgba(0,0,0,0.26);
}

input:focus {
    border-radius: 20px;
    padding: 10px;
    border: 0,5px solid black;

}

.mainButt { 
    margin-left: 10px;
    border-radius: 20px;
    padding: 10px;
    border: none;
    box-shadow:4px 4px 10px rgba(0,0,0,0.26);
    width:60px;
    transition:  .3s ease;
    border: 1px solid transparent;
}

.mainButt:hover {
    border-radius: 20px;
    padding: 10px;
    border: 0,5px solid black;
box-shadow:6px 6px 12px rgba(255,255,255,0.36);
}

.mainButt:active {
    border: 1px solid rgba(128,128,128, 0.4);
    box-sizing: border-box;
}

</style>