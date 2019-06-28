<template>
  <el-row type="flex" class="row-bg" justify="center" align="middle">
    <el-col :xs="14" :sm="12" :md="10" :lg="8" :xl="6">
      <div class="grid-content bg-purple-light">
        <el-form
          ref="form"
          :model="form"
          class="login-form"
          :rules="formRules"
          label-position="top"
          label-width="80px"
        >
          <el-form-item label="用户名" prop="username">
            <el-input v-model="form.username"></el-input>
          </el-form-item>
          <el-form-item label="密码" prop="password">
            <el-input v-model="form.password"></el-input>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="submitForm('form')" >登录</el-button>
            <el-button @click="resetForm('form')">重置</el-button>
          </el-form-item>
        </el-form>
      </div>
    </el-col>
  </el-row>
</template>


<script>
import axios from "axios"
export default {
  data() {
    return {
      form: {
        username: "",
        password: "",
      },
      formRules: {
        username: [
          { required: true, message: "请输入用户名", trigger: "blur" },
          { min: 5, max: 12, message: "用户名必须是5个到12个字符", trigger: "change" }
        ],
        password: [
          { required: true, message: "请输入密码", trigger: "blur" },
          { min: 6, max: 15, message: "密码必须是6个到15个字符", trigger: "change" }
        ]
      }
    };
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          axios({
            url: "http://localhost:8888/api/private/v1/login",
            method: "post",
            data: this.form
          }).then(({data: {data, meta}}) => {
            if(meta.status === 200) {
              localStorage.setItem("token", data.token)
              this.$router.push("/home")
            }
          })
        } else {
          // console.log("error submit!!");
          return false;
        }
      })
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
};
</script>
  
<style>
.row-bg {
  height: 100%;
  background-color: #2d434c;
}
.login-form {
  background-color: #ffffff;
  border-radius: 10px;
  padding: 30px 20px;
  min-width: 400px;
}
</style>



