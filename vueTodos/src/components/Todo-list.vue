<template>
    
                <div class="cal-6 mb-3">
                    <div class="nav nav-tabs" id="nav-tab" role="tablist">
                        <a href="#" class="nav-item nav-link active font-weight-bold" id="nav-home-tab">undone <span class="badge badge-second">9</span></a>
                        <a href="#" class="nav-item nav-link font-weight-bold" id="nav-profile-tab">done <span class="badge badge-success">9</span></a>
                    </div>
                </div>
                <Todo v-for="(item , index) in todos" :todo="item" :key="index" @delete-todo="$emit('delete-todo' , $event)" @edit-todo="$emit('edit-todo', $event)"></Todo>
            
</template>

<script>
import Todo from './Todo.vue'; 
export default{
    components:{
        Todo,
    },

    emits:['edit-todo' , 'delete-todo'],

    props:{
        todos:{
            type:Array,
            required: true
        }
    }
}

</script>