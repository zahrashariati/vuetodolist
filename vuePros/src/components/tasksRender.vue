<template>
    <div :key="task.id" v-for="task in tasks">
        <TaskIn @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"></TaskIn>
        
    </div>
</template>

<script>

import TaskIn from './TaskIn.vue';

    export default{
        name: 'tasksRender',
        props:{
            tasks:Array,
        },

        components:{
            TaskIn,
        },

        emits:['delete-task', 'toggle-reminder'],


    }

</script>