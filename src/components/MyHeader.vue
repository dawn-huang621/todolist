<template>
    <div>
        <input class="header" type="text" placeholder="請輸入任務名稱" v-model="title" style="width: 100%; height:50px;" @keyup.enter="add">
    </div>
</template>

<script>
import {nanoid} from 'nanoid'
export default {
    name:'MyHeader',
    props:['addTodo'],
    data(){
        return{
            title:''
        }
    },
    methods:{
        add(){
            //較驗數據
            if(!this.title.trim())return alert('輸入不能為空')
            const todoObj = {id:nanoid(),title:this.title,done:false};
            //通知app組件去添加一個todo對象
            this.addTodo(todoObj)
            //清空輸入
            this.title = ''
        }
    }
}
</script>

<style>
.header{
  margin-top: 10px;
  border: 1px solid rgb(184, 184, 184);
  border-radius: 5px;
}
</style>