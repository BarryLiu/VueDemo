<template>
   <li @click="handleClick">{{content}}_{{index}}</li>
</template>

<script>
export default {
  props:['content','index'],//接收从外面传进来的名字为 content 和 index 的值,
  methods: {
    handleClick(){
      //alert(this.content+"_"+this.index);
      this.$emit('delete', this.index);   //调用外面的 delete方法, 发布订阅模式, 父子组件传值

    }
  },
}

</script>

 <!-- scoped 作用域, 表示里面的 css样式只影响到此页面,如果去掉, 可能会影响到外面相同 className 的样式 -->
<style scoped> 
 
</style>
