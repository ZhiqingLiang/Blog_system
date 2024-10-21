<template>
  <div>
    <h2>Register page</h2>
    <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
    <el-form-item label="用户名" prop="username">
      <el-input type="text" v-model="username" ></el-input>
    </el-form-item>
    <el-form-item label="密码" prop="password">
      <el-input type="password" v-model="password"></el-input>
    </el-form-item>
    <el-form-item label="再次确认密码" prop="passwordAgain">
      <el-input type="password" v-model="passwordAgain"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="submitForm">提交</el-button>
      <el-button @click="resetForm">重置</el-button>
      <el-button @click="gotoLogin">登录</el-button>
    </el-form-item>
  </el-form>
</div>
</template>

<style scoped>
  h2{
    text-align: center;
    margin-top: 2rem;
    font-size: 50px;
    color: #4F709C;
  }
  .demo-ruleForm{
    width: 25rem;
    background-color: rgb(255, 255, 255,0.5);
    padding: 2rem;
    margin: 1rem auto;
  }
</style>
<script>
export default {
  data(){
    return{
      username:'',
      password :'',
      passwordAgain :''
    }
   
  },
  methods:{
    submitForm(){
      console.log('开始提交注册表单...')
      const {username, password, passwordAgain} = this.ruleForm
      if(username===''||password===''||passwordAgain===''){
        alert('请填写完完整的表单')
      }else if(password !== passwordAgain){
        alert('两次输入的密码不对')
      }else{
        this.$router.push('/login')
      }
    },
    resetForm(){
      this.username='',
      this.password ='',
      this.passwordAgain=''
    },
    gotoLogin(){
      this.$router.push('/')
    }
  }
}
</script>