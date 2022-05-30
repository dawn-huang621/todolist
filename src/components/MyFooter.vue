<template>
    <div class="card footer" style="width: 100%; height:50px;">
        <div class="card-body" >
            已完成{{doneTotal}}/全部{{todos.length}}//{{todos[2].done}}
        </div>
    </div>
</template>

<script>
export default {
    name:'MyFooter',
    props:['todos'],
    computed:{
        doneTotal(){
            let i = 0;
            this.todos.forEach((todo) => {
                if(todo.done) i++
            })
            return i
        }
    },
}
</script>

<style>
.footer{
    margin-top: 10px;
}
</style>