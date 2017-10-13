<template>
  <div>
<el-row>
  <el-tree
  :data="data2"
  show-checkbox
  node-key="id"
  :props="defaultProps">
</el-tree>
</el-row>
<template>
    <el-table :data="list" v-loading.body="listLoading" element-loading-text="拼命加载中" border fit highlight-current-row>
      <el-table-column align="center" label='ID' width="95">
        <template scope="scope">
          {{scope.$index}}
        </template>
      </el-table-column>
      <el-table-column label="Title">
        <template scope="scope">
          {{scope.row.title}}
        </template>
      </el-table-column>
      <el-table-column label="Author" width="110" align="center">
        <template scope="scope">
          <span>{{scope.row.author}}</span>
        </template>
      </el-table-column>
      <el-table-column label="Pageviews" width="110" align="center">
        <template scope="scope">
          {{scope.row.pageviews}}
        </template>
      </el-table-column>
      <el-table-column class-name="status-col" label="Status" width="110" align="center">
        <template scope="scope">
          <el-tag :type="scope.row.status | statusFilter">{{scope.row.status}}</el-tag>
        </template>
      </el-table-column>
      <el-table-column align="center" prop="created_at" label="Display_time" width="200">
        <template scope="scope">
          <i class="el-icon-time"></i>
          <span>{{scope.row.display_time}}</span>
        </template>
      </el-table-column>
    </el-table>
</template>
  </div>
</template>


<script>
  export default {
    data() {
      return {
        data2: [{
          id: 1,
          label: '广州XXXX科技有限公司',
          children: [{
            id: 4,
            label: '销售部',
            children: [{
              id: 9,
              label: '销售分组1'
            }, {
              id: 10,
              label: '销售分组2'
            }]
          },
          {
            id: 2,
            label: '研发部',
            children: [{
              id: 5,
              label: '研发php'
            }, {
              id: 6,
              label: '研发c++'
            },{
              id: 7,
              label: '研发android'
            }]
          },
          {
            id: 11,
            label: '技术支持',
            children: [{
              id: 12,
              label: '技术支持1'
            }, {
              id: 13,
              label: '技术支持2'
            },{
              id: 14,
              label: '技术支持3'
            }]
          }
          ]
        }],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      };
    }
  };
</script>