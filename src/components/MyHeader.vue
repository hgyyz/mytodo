<template>
    <div>
        <div class="todo-header">
            <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model = "name" @keyup.enter = "add"/>
          </div>
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
    props: ["addTodo"],
    data(){
        return{
            name:''
        }
    },
    methods:{
        add(){
            //校验数据
            if(!this.name.trim()) return alert("输入不能为空")
            //将用户的输入包装成一个对象
            const todoObj = {id:Date.now(),name:this.name,done:false}
            //通知App添加一个todo
            this.addTodo(todoObj)
            //清空输入框
            this.name = ''
        }
    },
    
}
</script>

<style scoped>
/*header*/
.todo-header input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}

.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
}
</style>