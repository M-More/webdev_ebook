<template>
  <div id="app">
    <div id="heading">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <p id="title">e-Book</p>
        <p id="subtitle">图书详情</p>
        <el-button type="text" class="head_nav_button"><a href="#">退出登录</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">我的订单</a></el-button>
        <el-button type="text" class="head_nav_button"><a href="#">购物车</a></el-button>
      </el-menu>
      <div class="line"></div>
    </div>

    <div class="main_body">
      <div class="content">
        <div class="buying">
          <div class="bookimg"><img src="../../assets/images/list/3.jpg" width="300px"></div>
          <div class="bookinfo">
            <p class="bookname">苏菲的世界（新版）</p>
            <p class="bookname2">二十世纪百部经典名著之一 全球销量超过4500万册</p>
            <p class="writer">作者:乔斯坦·贾德  出版社:作家出版社  出版时间:2017年09月</p>
            <p class="ISBN">ISBN：9787544270878</p>
            <p class="price">¥25.40</p>
            <p class="stock">库存：1000</p>

            <p>购买数量：</p>

            <el-input-number v-model="num1" @change="handleChange" :min="1" :max="10" label="描述文字"></el-input-number>
            <br/>
            <el-button type="primary">加入购物车</el-button>

          </div>
        </div>
        <div class="detail">
          <h3>编辑推荐</h3>
          <p>《苏菲的世界》全球销量超过45000000册  翻译成64种语言出版</p>
          <p>《苏菲的世界》二十世纪百部经典名著之一  中小学生推荐必读图书</p>
          <p>《苏菲的世界》*简明有趣的哲学入门书   *温故知新的哲学历程录</p>
          <br/>
          <h3>内容简介</h3>
          <p>
            14岁的少女苏菲不断接到一些极不寻常的来信，世界像谜团一般在她眼底展开，她在一位神秘导师的指引下，苏菲开始思索，从苏格拉底、柏拉图到达尔文、弗洛伊德等哲学大师所思考的根本问题。苏菲运用少女天生的悟性与后天知识，企图解开这些谜团，然而，事实真相远比她所想的更怪异、更离奇。《苏菲的世界》，是智慧的世界，梦的世界。它将会唤醒每个人内心深处对生命的赞叹与对人生终极意义的关怀与好奇。
          </p>
          <br/>
          <h3>作者简介</h3>
          <p>
            乔斯坦·贾德，1952年生于挪威，曾担任高中哲学教师多年。1986年出版第一部作品《贾德谈人生》，迄今出版了19部作品。长篇小说《苏菲的世界》翻译成64种语言，全球销量超过4500万册，被誉为“20世纪百部经典著作之一”，此书也奠定了贾德全球十大作家的地位。贾德的主要作品有《没有肚脐的小孩》《苏菲的世界》《纸牌的秘密》《圣诞的故事》《主教的情人》《玛雅》《橙色女孩》等。乔斯坦·贾德用丰富的想象力和高超的讲故事手法，吸引了整个世界，其作品始终执著于人生本质与人生终极意义的探索与思考。
          </p>

        </div>
      </div>
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
      sum: 95,
      num1: 1
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
  @import "../../assets/css/info.css";
</style>
