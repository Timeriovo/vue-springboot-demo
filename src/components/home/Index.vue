<template>
  <el-table
    :data="tableData"
    stripe
    style="width: 100%">
    <el-table-column
      prop="id"
      label="ID"
      width="100">
    </el-table-column>
    <el-table-column
      prop="userAcct"
      label="用户名"
      width="180">
    </el-table-column>
    <el-table-column
      prop="password"
      label="密码"
      width="180">
    </el-table-column>
    <el-table-column
      prop="nickname"
      label="昵称"
      width="180">
    </el-table-column>
  </el-table>
</template>

<script>
  export default {
    name:'Index',
    data() {
      return {
        tableData: []
      }
    },
    mounted: function () {

      var _this = this;//很重要！！
      console.log(_this===this);
      this.$axios.get('/admin')
        .then(function (res) {
          _this.tableData = res.data.object
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  }
</script>
