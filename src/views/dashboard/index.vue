<template>
  <div class="dashboard-container">
    <div class="dashboard-text">
      <el-row :gutter="20">
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="18">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="18">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <el-card class="box-card"></el-card>
          </div>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Dashboard",
  computed: {
    ...mapGetters(["name"])
  }
};
</script>

<style lang="scss" scoped>
.dashboard {

  &-container {
    margin: 20px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}

.el-row{
  margin-bottom: 15px;
}
</style>
