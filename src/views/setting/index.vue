<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="签到时间：">
          <el-time-picker type="fixed-time" placeholder="Pick a time" v-model="form.date2" style="width: 100%;"></el-time-picker>
      </el-form-item>
      <el-form-item label="签离时间：">
          <el-time-picker type="fixed-time" placeholder="Pick a time" v-model="form.date2" style="width: 100%;"></el-time-picker>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">保存</el-button>
      </el-form-item>
    </el-form>

    <el-form ref="form2" :model="form2" label-width="120px">
      <el-form-item label="原始密码：">
        <el-input v-model="form.oldPassword"></el-input>
      </el-form-item>      
      <el-form-item label="新密码：">
        <el-input v-model="form.newPassword"></el-input>
      </el-form-item>      
      <el-form-item label="新密码：">
        <el-input v-model="form.newPassword1"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">保存</el-button>
      </el-form-item>
    </el-form>

  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
  methods: {
    onSubmit() {
      this.$message('submit!')
    }
  }
}
</script>
