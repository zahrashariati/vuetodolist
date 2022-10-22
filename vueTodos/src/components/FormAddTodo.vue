<template>
    <div class="form-inline">
        <div class="form-group mb-3">
            <input type="text" v-model="todoText" class="form-control mb-2" placeholder="i want to do ...">
            <button class="btn btn-primary input-group-text" @click="addTodo">add</button>
        </div>
    </div>
</template>

<script>

export default{
    data(){
        return{
            todoText : ""
        }
    },
    emits:['add-todo'],
    methods:{
        addTodo(){
            this.$emit('add-todo' , this.todoText);
            this.todoText="";
        }
    }
}


</script>

<style>

.vertical-center {
  margin: 0;
  position: absolute;
  top: 27%;
  left: 58%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
</style>