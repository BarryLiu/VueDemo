<template>
    <div>
        <h1>todoList</h1>
        <h3>简单添加节点，删除节点</h3>
        <h6>
            实现: 文本框输入内容, 分别到下面ul中添加 li,显示其输入的内容以及下标, 点击此li ,删除自己
        </h6>
        <br>

        <input v-model="inputValue">
        <button @click="handleSubmit">添加</button>

        <h2>双向绑定实现实现</h2>
        <ul>
            <li v-for="(item, index) in list" :key="index" @click="handleDeleteSelf(index)">
                {{item}}_{{index}} 
            </li>
        </ul>
        <hr/>
        
        <h2>用组件实现</h2>
        <ul>
            <todo-item v-for="(item, index) in list" :key="index" 
            :content="item" 
            :index="index"
            @delete="handleDelete"
            ></todo-item>
        </ul>

        <hr/>
        {{inputVal}}

    </div>   
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
    components:{
        "todo-item":TodoItem
    },

    data(){
        return {
            inputValue:"",
            list:[]
        }
    },
    methods: {
        handleSubmit(){
            this.list.push(this.inputValue)
            this.inputValue=''
        },
        handleDelete(index){
            this.list.splice(index,1);
        },
        handleDeleteSelf(index){
            this.list.splice(index,1);
        }
    },
    watch: {//监听指定值, F12 查看 控制台看得到,有输入监听就触发打印
        inputValue: function(newVal,oldVal){
            console.log("newVal: "+newVal+" oldVal: "+oldVal)
        }
    },
    computed: {//监听实例以内的值, 计算属性
        inputVal: function(){
            return "computed: "+this.inputValue
        }
    },
}
</script>

<style>
 
</style>
