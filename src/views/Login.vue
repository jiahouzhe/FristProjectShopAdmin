<template>
  <el-row type="flex" class="row-bg" justify="center" align="middle">
    <el-col :xs="14" :sm="12" :md="10" :lg="8" :xl="6">
      <div class="grid-content bg-purple-light">
        <el-form ref="form" :model="form" class="login-form" label-position="top" label-width="80px">
          <el-form-item label="用户名">
            <el-input v-model="form.username"></el-input>
          </el-form-item>
          <el-form-item label="密码">
            <el-input v-model="form.password"></el-input>
          </el-form-item>
          <el-form-item>
            <el-button type="primary" @click="onSubmit">登录</el-button>
            <el-button>重置</el-button>
          </el-form-item>
        </el-form>
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  data() {
    return {
      form: {
        username: "",
        password: "",
        type: []
      }
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    }
  }
};
</script>
  
<style>
  .row-bg {
    height: 100%;
    background-color: #2D434C;
  }
  .login-form {
    background-color: #ffffff;
    border-radius: 10px;
    padding: 30px 20px;
    min-width: 400px;
  }
</style>



