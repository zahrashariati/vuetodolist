<template>
   <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '' , 'task']">
        <h3>
            {{task.text}}
            <button @click="onDelete(task.id)">Delete</button>
        </h3>
        <p>{{task.day}}</p>
   </div> 
    
</template>

<script>
    export default{
        name: 'TaskIn',
        props:{
            task:Object,
        },

        methods:{
            onDelete(id){
                this.$emit('delete-task', id)
            }
        },
    }
</script>

<style scoped>

    button{
        background-color: red;
        border-radius: 5px;
        width: 60px;
        height: 30px;
        margin-top: 4px;
        
    }

    .fas{
        color: red;

    }

    .task{
        background-color: #b8b4b4;
        margin: 5px;
        padding: 10px 20px;
        cursor: pointer;
    }

    .task.reminder{
        border-left: 5px solid green;
    }

    .task h3{
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

</style>