<template>
    <header>
        <h1>{{title}}</h1>
        <CustomButton @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red': 'green'"></CustomButton>
        
    </header>
</template>

<script>

import CustomButton from './CustomButton.vue';
    export default{
        components:{
            CustomButton,
    
},
        name: 'CustomHeader',
        props:{
            title : String,
            showAddTask : Boolean,
    
        },
    }
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }

</style>