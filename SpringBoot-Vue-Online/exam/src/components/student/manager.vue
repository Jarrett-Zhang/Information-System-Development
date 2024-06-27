<!--管理中心-->
<template>
  <div id='manager'>
    <el-form :model="ruleForm2" status-icon :rules="rules2" ref="ruleForm2" label-width="100px" class="demo-ruleForm">
      <h3 class="alter">修改你的密码</h3>
        <el-form-item label="密码" prop="pass" class="pass">
        <el-input type="password" v-model="ruleForm2.pass" autocomplete="off"></el-input>
      </el-form-item>
      <el-form-item label="确认密码" prop="checkPass">
        <el-input type="password" v-model="ruleForm2.checkPass" autocomplete="off"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="submitForm('ruleForm2')">提交</el-button>
        <el-button @click="resetForm('ruleForm2')">重置</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>


<style scoped>
#manager .pass  label{
  color: red;
  font-size: 20px;
}
#manager {
  width: 600px;
  margin: 0 auto;
  margin-top: 100px;
  text-align: center;
  margin-bottom: 300px;
}
#manager .alter {
  margin: 30px 0px;
}
</style>
