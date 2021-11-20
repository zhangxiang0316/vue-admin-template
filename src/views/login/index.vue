<template>
  <div class="login-container">
    <div class="header">
      <div class="content">
        <img class="logo" src="../../assets/404_images/404_cloud.png" @click="$router.push('/news/index')">
        <div style="font-size: 16px;margin: 0 10px;font-weight: 800;flex: 1">原子回声科技有限公司</div>
        <img class="logo" src="../../assets/404_images/404_cloud.png" @click="$router.push('/news/index')">
        <div style="font-size: 16px;margin: 0 10px;font-weight: 800">原子回声</div>
      </div>
    </div>
    <el-card style="height: 400px;width: 350px;position: absolute;right: 20%;top:20%">
      <el-form :model="loginForm">
        <el-form-item>
          <el-input placeholder="请输入手机号" v-model="loginForm.phone">
            <template slot="prepend">+86</template>
          </el-input>

        </el-form-item>

      </el-form>
    </el-card>
  </div>
</template>

<script>

export default {
  name: 'Login',
  data() {
    return {
      loginForm: {
        username: 'admin',
        password: '111111'
      },
      loading: false,
      passwordType: 'password',
      redirect: undefined
    }
  },
  watch: {
    $route: {
      handler: function(route) {
        this.redirect = route.query && route.query.redirect
      },
      immediate: true
    }
  },
  methods: {
    handleLogin() {
      this.$refs.loginForm.validate(valid => {
        if (valid) {
          this.loading = true
          this.$store.dispatch('user/login', this.loginForm).then(() => {
            this.$router.push({ path: this.redirect || '/' })
            this.loading = false
          }).catch(() => {
            this.loading = false
          })
        } else {
          console.log('error submit!!')
          return false
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped>

.header {
  width: 100%;
  height: 50px;
  line-height: 50px;
  color: white;
  background: #2EC13C;

  .logo {
    width: 40px;
    height: 40px;
    margin: 5px 0px 5px 20px
  }

  .content {
    margin: 0 auto;
    display: flex;
  }
}

.login-container {
  min-height: 100%;
  width: 100%;
  background-color: #fff;
  overflow: hidden;

}
</style>
