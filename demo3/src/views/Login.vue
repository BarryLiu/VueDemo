<template>
    <div >
        

        <form action="" v-if="!isReg">
            用户名: 
             <input type="text" v-model="username" >

            密码：
            <input type="text" v-model="password" >
            <button @click="login()">登录</button>
            <button @click="goReg()">注册</button>
        </form>
        <form action="" v-else>
            用户名: 
            <input type="text" v-model="username" >

            密码：
            <input type="text" v-model="password" >
            再次输入密码：
            <input type="text" v-model="repect" >
            
            <button @click="reg()">注册</button>
            <button @click="canal()">返回</button>

        </form>

    </div>
</template>

<script>
export default {
    data(){
       return{
           isReg:false,
           username:'',
           password:'',
           repect:''

       } 
    },
    methods: {
        login(){

        },

        reg(){
            
        },
        goReg(){
            this.isReg = true
        },
        canal(){
            this.isReg = false
        }
    },

}
</script>



<style scoped>

</style>
