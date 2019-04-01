<template>
  <div id="app">
    <div id="heading">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <p id="title">e-Book</p>
        <p id="subtitle">订单统计</p>
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
        label="下单时间"
        prop="time">
      </el-table-column>
      <el-table-column
        label="下单用户"
        prop="username">
      </el-table-column>
      <el-table-column
        label="书名"
        prop="bookname">
      </el-table-column>
      <el-table-column
        label="金额"
        prop="price">
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{
        time: '2019-03-31 18:17:26',
        username: '张三',
        bookname: '追风筝的人',
        price: 29.9.toFixed(2)
      }, {
        time: '2019-03-31 18:17:25',
        username: '李四',
        bookname: '摆渡人',
        price: 29.7.toFixed(2)
      }, {
        time: '2019-03-31 18:17:24',
        username: '王五',
        bookname: '人间失格',
        price: 29.2.toFixed(2)
      }, {
        time: '2019-03-31 18:17:23',
        username: '张三',
        bookname: '苏菲的世界',
        price: 25.2.toFixed(2)
      }, {
        time: '2019-03-31 18:16:23',
        username: '王五',
        bookname: '百年孤独',
        price: 23.2.toFixed(2)
      }, {
        time: '2019-03-30 12:17:24',
        username: '王五',
        bookname: '斜阳',
        price: 29.3.toFixed(2)
      }, {
        time: '2019-03-31 09:17:23',
        username: '王五',
        bookname: '李尔王',
        price: 29.2.toFixed(2)
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
