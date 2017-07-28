<template>
    
    <div class="base">

      <div class="msg">

            <span>名称：</span >
            <span>某网站</span >

            <span class="website">网址：</span >
             <span>*******</span >

      </div>

       <el-form :inline="true" :model="formInline" class="demo-form-inline">
            <el-form-item label="Session信息：">
              <el-input v-model="formInline.user" placeholder="key"></el-input>
            </el-form-item>
            <el-form-item>
              <el-input v-model="formInline.user" placeholder="value"></el-input>
            </el-form-item>
            <i class="el-icon-plus" @click="addSession()"></i>
        </el-form>
        
       <el-form :inline="true" :model="formInline" class="demo-form-inline">
            <el-form-item label="Cookie信息 ：">
              <el-input v-model="formInline.user" placeholder="key"></el-input>
            </el-form-item>
            <el-form-item>
              <el-input v-model="formInline.user" placeholder="value"></el-input>
            </el-form-item>
            <i class="el-icon-plus" ></i>
        </el-form>
          
         <el-form-item label-width="100px">
            <el-button type="primary" @click="submitForm('ruleForm')">下一步</el-button>
            <el-button @click="resetForm('ruleForm')">重置</el-button>
         </el-form-item>
    </div>

</template>
<script>
  export default {
    data() {
      return {
        formInline: {
          user: '',
          region: ''
        }
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
      },
      addSession(){
        alert("123")
      }
    }
  }
</script>

<style scoped>
    .base{
         margin: 47px 327px;
         width: 640px;
    }
    .msg {
      margin-bottom: 20px;
    }
    .website {
      margin-left: 208px;
    }
    .el-icon-plus {
      margin-top: 9px;
    }

</style>