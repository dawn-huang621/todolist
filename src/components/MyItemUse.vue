<template>
    <li class="list-group-item" style="height:50px;">
    <input type="checkbox"
        class="confirmationBox"
        :checked="mytodo.done" 
        name="subscribe" 
        value="html-newsletter">
    <span>{{todo.title}}</span>
    <button type="button" class="btn btn-danger">刪除</button>
    </li>
</template>

<script>
export default {
    name:'MyItemUse',
    data(){
        return{
            // mydone:this.todo.done
            mytodo:this.todo
        }
    },
    //聲明接收todo對象
    props:['todo'],
}
</script>

<style>
.confirmationBox{
    margin-top: 10px;
    margin-bottom: 10px;
    cursor: pointer;
    background: pink;
}
span{
    position: absolute;
    top:50%;
    transform: translateY(-50%);
    padding-left: 30px;
}
.btn{
    position: relative;
    top:50%;
    transform: translateY(-50%);
    float: right;
    right: 10px;
    padding: 10px;
    opacity: 0;
    transition: all 1s 3s;
}
li:hover{
    background: rgb(201, 201, 201);
}
li:hover .btn{
    opacity: 1;
}
</style>