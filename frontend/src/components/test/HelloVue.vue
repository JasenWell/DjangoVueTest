<template>
  <div id="vue">
    Hello vue.js {{msg}}
    <el-button>默认按钮</el-button>
    <el-button type="primary">主要按钮</el-button>
    <el-button type="text">文字按钮</el-button>
  </div>
</template>

<script type="text/javascript">
   export default { //这里需要将模块引出，可在其他地方使用
    name: "HelloVue",
    data (){ //注意：data即使不需要传数据，也必须return,否则会报错
      return {
        msg: "啦啦啦啦啦"
      }
    }
  }
</script>

<style type="text/css">
  #vue{
    color: green;
    font-size: 28px;
  }
</style>
