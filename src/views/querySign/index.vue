<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="开始日期">
          <el-date-picker type="date" placeholder="Pick a date" v-model="form.date1" style="width: 100%;"></el-date-picker>
      </el-form-item>      
      <el-form-item label="结束日期">
          <el-date-picker type="date" placeholder="Pick a date" v-model="form.date2" style="width: 100%;"></el-date-picker>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">查询</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        date1: '',
        date2: '',
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
