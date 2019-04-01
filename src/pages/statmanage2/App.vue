<template>
  <div id="app">
    <div id="heading">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <p id="title">e-Book</p>
        <p id="subtitle">销量统计</p>
        <el-button type="text" class="head_nav_button"><a href="#">退出登录</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">订单统计</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">书籍管理</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">用户管理</a></el-button>
      </el-menu>
      <div class="line"></div>
    </div>

    <br/>

    <div class="block">
      <span class="demonstration">请选择时间范围：</span>
      <el-date-picker
        v-model="value6"
        type="daterange"
        range-separator="至"
        start-placeholder="开始日期"
        end-placeholder="结束日期">
      </el-date-picker>
    </div>

    <el-table
      :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
      style="width: 100%">
      <el-table-column
        label="书名"
        prop="bookname">
      </el-table-column>
      <el-table-column
        label="销量"
        prop="sellamount">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{
        bookname: '追风筝的人',
        sellamount: 9
      }, {
        bookname: '苏菲的世界',
        sellamount: 92
      }, {
        bookname: '摆渡人人',
        sellamount: 97
      }, {
        bookname: '李尔王',
        sellamount: 92
      }, {
        bookname: '麦克白',
        sellamount: 92
      }, {
        bookname: '哈姆雷特',
        sellamount: 33
      }, {
        bookname: '红楼梦',
        sellamount: 21
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
