<template>
  <div id="app">
    <div id="heading">
      <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <p id="title">e-Book</p>
        <p id="subtitle">用户登陆</p>
      </el-menu>
      <div class="line"></div>
    </div>

    <br/>
    <br/>

    <div id="form">
      <br/>
      <el-form :model="ruleForm02" status-icon :rules="rules2" ref="ruleForm02" label-width="100px" class="demo-ruleForm">
        <el-form-item label="用户名" prop="name">
          <el-input v-model="ruleForm02.name" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label="密码" prop="pass">
          <el-input type="password" v-model="ruleForm02.pass" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('ruleForm02')">登陆</el-button>
          <el-button @click="resetForm('ruleForm02')">重置</el-button>
        </el-form-item>
      </el-form>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    var validatePass = (rule, value, callback) => {
      if (value === '') {
        callback(new Error('请输入密码'))
      } else {
        if (this.ruleForm02.checkPass !== '') {
          this.$refs.ruleForm02.validateField('checkPass')
        }
        callback()
      }
    }
    return {
      ruleForm02: {
        name: '',
        pass: ''
      },
      rules2: {
        pass: [
          { validator: validatePass, trigger: 'blur' }
        ]
      }
    }
  },
  methods: {
    submitForm (formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!')
        } else {
          console.log('error submit!!')
          return false
        }
      })
    },
    resetForm (formName) {
      this.$refs[formName].resetFields()
    }
  }
}
</script>

<style>
  @import "../../assets/css/form.css";
</style>
