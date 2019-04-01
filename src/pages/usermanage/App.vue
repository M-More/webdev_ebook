<template>
  <div id="app">
    <div id="heading">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <p id="title">e-Book</p>
        <p id="subtitle">用户管理</p>
        <el-button type="text" class="head_nav_button"><a href="#">退出登录</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">订单统计</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">书籍管理</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">用户管理</a></el-button>
      </el-menu>
      <div class="line"></div>
    </div>

    <br/>

    <el-input
      v-model="search"
      size="medium"
      clearable
      placeholder="输入用户关键字搜索用户">
      <i slot="prefix" class="el-input__icon el-icon-search"></i>
    </el-input>

    <el-table
      :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
      style="width: 100%">
      <el-table-column
        label="用户名"
        sortable
        prop="name">
      </el-table-column>
      <el-table-column
        label="权限"
        prop="kind">
      </el-table-column>
      <el-table-column
        align="right" label="用户状态管理">
        <template slot-scope="scope">
          <el-switch
            style="display: block"
            v-model="scope.row.stat"
            active-color="#13ce66"
            inactive-color="#ff4949"
            active-text="正常"
            inactive-text="禁用">
          </el-switch>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{
        name: 'admin',
        kind: '管理员',
        stat: true
      }, {
        name: '张三',
        kind: '普通用户',
        stat: true
      }, {
        name: '李四',
        kind: '普通用户',
        stat: false
      }, {
        name: '王五',
        kind: '普通用户',
        stat: true
      }, {
        name: '赵六',
        kind: '普通用户',
        stat: true
      }, {
        name: '王小明',
        kind: '普通用户',
        stat: true
      }],
      search: ''
    }
  },
  methods: {
    handleEdit (index, row) {
      console.log(index, row)
    },
    handleDelete (index, row) {
      console.log(index, row)
    }
  }
}
</script>

<style>
  @import "../../assets/css/index.css";
</style>
