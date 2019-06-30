<template>
  <el-container>
    <el-header>
      <el-row type="flex" class="row-bg" justify="space-between" align="middle">
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <img src="../assets/logo.png" alt>
          </div>
        </el-col>
        <el-col>
          <div class="grid-content bg-purple-light">
            <div class="hometitle">品优购后台管理系统</div>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <div>
              欢迎39期星耀会员
              <a href="#">退出</a>
            </div>
          </div>
        </el-col>
      </el-row>
    </el-header>
    <el-container>
      <el-aside width="200px">Aside</el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {};
</script>

<style>
.el-header {
  padding: 0 !important;
  background-color: #b1c1cd;
}
.row-bg {
  background-color: #b1c1cd;
}
.hometitle {
  font-size: 28px;
  font-weight: 700;
  color: #ffffff;
  text-align: center;
}
.bg-purple div {
    font-weight: bolder;
    text-align: right;
    padding-right: 20px;
}

.bg-purple div a {
    color: orange;
}
</style>
