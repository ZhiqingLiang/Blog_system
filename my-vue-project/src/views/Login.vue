<template>
  <div>
    <h2>Login page</h2>
    <el-form :model="loginForm" ref="loginForm" label-width="100px" class="loginForm">
      <div class="c">
      <el-form-item label="用户名" prop="username">
        <el-input v-model="username" aria-placeholder="username" class="custom-input"></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input type="password" v-model="password" aria-placeholder="password" class="custom-input"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="submitForm">提交</el-button>
        <el-button @click="resetForm">重置</el-button>
        <el-button @click="goToRegister" >注册</el-button>
      </el-form-item>
      </div>
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
  .loginForm{
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
      password:''
    }
  },
  methods:{
    submitForm(form){
      console.log('submit form....',this.username,this.password)
      if(form){
        if(this.username === 'vanya' && this.password === '0930'){
          alert('成功登录')
          this.$router.push('/article')
        }
      }else{
        alert('失败！')
        this.resetForm();
      }
    },
    resetForm(){
      this.username = '';
      this.password = '';
    },
    goToRegister() {
    this.$router.push('/register');
  }
  }

}
</script>
