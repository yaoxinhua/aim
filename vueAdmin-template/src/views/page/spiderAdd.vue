<template>
    <div class="base">
      <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm" style="width:500px; margin: 20px auto">
          <el-form-item label="名称" prop="name">
            <el-input v-model="ruleForm.name"></el-input>
          </el-form-item>
          <el-form-item label="网址" prop="webSize">
            <el-input v-model="ruleForm.webSize"></el-input>
          </el-form-item>
          <el-form-item label="层级" prop="level">
            <el-input v-model="ruleForm.level"></el-input>
          </el-form-item>
          <el-form-item label="编码" prop="codeStyle">
            <el-input v-model="ruleForm.codeStyle"></el-input>
          </el-form-item>
           <el-form-item label="信息" prop="message">
            <el-input v-model="ruleForm.message"></el-input>
          </el-form-item>
          <el-form-item label="请求方式" prop="requestMethod">
            <el-radio-group v-model="ruleForm.requestMethod">
              <el-radio label="get"></el-radio>
              <el-radio label="post"></el-radio>
            </el-radio-group>
          </el-form-item>
          <el-form-item label="登录" prop="sign">
            <el-checkbox-group v-model="ruleForm.sign">
              <el-checkbox label="是否登录" name="sign"></el-checkbox>
            </el-checkbox-group>
          </el-form-item>
          <el-form-item label-width="100px">
            <el-button type="primary" @click="submitForm('ruleForm')">下一步</el-button>
            <el-button @click="resetForm('ruleForm')">重置</el-button>
          </el-form-item>
      </el-form>
    </div>

</template>
<script>
  export default {
    data() {
      return {
        ruleForm: {
          name: '',
          webSize: '',
          level: '',
          codeStyle: '',
          message: '',
          requestMethod: false,
          sign: ''
        },
        rules: {
          name: [
            { required: true, message: '请输入名称', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
          ],
          webSize: [
            { required: true, message: '请输入网址', trigger: 'blur' }
          ],
          level: [
            {  required: true, message: '请输入层级', trigger: 'blur' }
          ],
          codeStyle: [
            {  required: true, message: '请输入编码格式', trigger: 'blur' }
          ],
          message: [
            {  required: true, message: '请输入商品信息', trigger: 'blur' }
          ],
          requestMethod: [
            { required: true, message: '请选择请求方式', trigger: 'change' }
          ],
          sign: [
            {  required: false}
          ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
  }
</script>
<style scoped>
    .base{
      width:"100px";
      margin: auto;

    }
</style>
