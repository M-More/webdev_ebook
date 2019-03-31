<template>
  <div id="app">
    <div id="heading">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <p id="title">e-Book</p>
        <p id="subtitle">购物车</p>
        <el-button type="text" class="head_nav_button"><a href="#">退出登录</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">我的订单</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">购物车</a></el-button>
      </el-menu>
      <div class="line"></div>
    </div>

    <br/>

    <el-table
      :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
      style="width: 100%">
      <el-table-column label="封面">
        <template slot-scope="scope">
          <img :src="scope.row.cover" class="head_pic" width="120px"/>
        </template>
      </el-table-column>
      <el-table-column
        label="书名"
        prop="name">
      </el-table-column>
      <el-table-column
        label="单价"
        prop="price">
      </el-table-column>
      <el-table-column label="数量">
        <template slot-scope="scope">
          <el-input-number v-model="scope.row.amount" @change="handleChange(scope.row)" :min="1"></el-input-number>
        </template>
      </el-table-column>
      <el-table-column
        label="小计"
        prop="sum">
      </el-table-column>
      <el-table-column
        align="right">
        <template slot="header" slot-scope="scope">
        </template>
        <template slot-scope="scope">
          <el-button
            size="mini"
            type="danger"
            @click="handleDelete(scope.$index, scope.row)">删除</el-button>
        </template>
      </el-table-column>
    </el-table>

    <div id="summary">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <div id="sumprice" style="float: right">
        </div>
      </el-menu>
      <div class="line"></div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{
        name: '解忧杂货店',
        price: 23.9.toFixed(2),
        amount: 1,
        cover: require('../../assets/images/list/1.jpg'),
        sum: 23.9.toFixed(2)
      }, {
        name: '摆渡人',
        price: 22.9.toFixed(2),
        amount: 1,
        cover: require('../../assets/images/list/2.jpg'),
        sum: 22.9.toFixed(2)
      }, {
        name: '人间失格',
        price: 13.9.toFixed(2),
        amount: 1,
        cover: require('../../assets/images/list/3.jpg'),
        sum: 13.9.toFixed(2)
      }, {
        name: '月亮和六便士',
        price: 34.9.toFixed(2),
        amount: 1,
        cover: require('../../assets/images/list/4.jpg'),
        sum: 34.9.toFixed(2)
      }],
      search: '',
      sum: 95
    }
  },
  methods: {
    handleChange: function (value) {
      value.sum = (value.amount * value.price).toFixed(2)
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
