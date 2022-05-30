<template>
    <div class="card list" style="width: 100%; height: auto;">
    <ul class="list-group list-group-flush">
        <MyItemUse v-for="todoObj in todos"
        :key="todoObj.id" 
        :todo="todoObj" 
        :checkTodo="checkTodo" 
        :deleteTodo="deleteTodo"></MyItemUse>
    </ul>
    </div>
</template>

<script>
import MyItemUse from '@/components/MyItemUse.vue'

export default {
    name:'MyList',
    props:['todos','checkTodo','deleteTodo'],
    components: { MyItemUse },
}
</script>

<style>
.list{
  margin-top: 10px;
}
</style>