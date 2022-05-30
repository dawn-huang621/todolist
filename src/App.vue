<template>

<div class="container">
  <div class="row align-items-start">
    <div class="col">
    </div>
    <div class="col">
    </div>
    <div class="col">
    </div>
  </div>
  <div class="row align-items-center">
    <div class="col">
    </div>
    
    <div class="col taskList">
    <!-- header -->
      <MyHeader :addTodo="addTodo"></MyHeader>
      <!-- list -->
      <MyList 
        :todos="todos" 
        :checkTodo="checkTodo" 
        :deleteTodo="deleteTodo"
      ></MyList>
      <!-- footer -->
      <MyFooter :todos="todos"></MyFooter>
    </div>

    <div class="col">
    </div>
  </div>
  <div class="row align-items-end">
    <div class="col">
    </div>
    <div class="col">
    </div>
    <div class="col">
    </div>
  </div>
</div>


</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyList from './components/MyList.vue'
import MyFooter from './components/MyFooter.vue'

export default{
  components: { MyHeader,MyList,MyFooter },
  data(){
      return{
          todos:[
              {id:"001",title:"睡覺",done:"false"},
              {id:"002",title:"吃飯",done:"true"},
              {id:"003",title:"寫作業",done:"false"},
          ]
      }
  },
  methods:{
    addTodo(todoObj){
      // console.log("資料傳遞成功",x)
      this.todos.unshift(todoObj)
    },
    //勾選或取消
    checkTodo(id){
        this.todos.forEach((todo) => {
            console.log(todo.id)
            if(this.todos.id === id ) todo.done = !todo.done
        });
    },
    deleteTodo(id){
      this.todos = this.todos.filter( todo => todo.id !== id)
    }
  },
}
</script>


<style lang="scss">
@import '~bootstrap/scss/bootstrap'; 
*{
  padding: 0px;
  margin: 0px;
}
html,body{
  height: 100%;
  border: 2px solid rgb(255, 145, 0);
}
.container{
  // height: 800px;
  border: 2px solid rgba(196, 83, 49, 0.74);
}
.row{
  padding: 10px;
  height: 200px;
}
.row:nth-child(2){
  height: 500px;
}
.taskList{
  border: 2px solid rgb(255, 145, 0);
  height: 100%;
  background: rgb(252, 225, 104);
  margin: 10px;
  border-radius: 10px;
  box-shadow: 10px 10px 25px saddlebrown;
}
</style>
