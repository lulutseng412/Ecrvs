<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Vue 後台管理系統</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon" />
    </button>
    <div id="navbarSupportedContent" class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <router-link class="nav-link" to="/dashboard/products">產品列表</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/dashboard/coupons">優惠卷列表</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/dashboard/imagersview">圖片頁面</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/dashboard/orders">訂單列表</router-link>
        </li>
        <!--
        <li class="nav-item">
          <router-link class="nav-link" :to="{ name: '用戶訂單'}">模擬下單系統</router-link>
        </li>-->
        <li class="nav-item">
          <a class="nav-link" href="#" @click.prevent="signOut">登出</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Sidebar',
  data () {
    return {}
  },
  methods: {
    signOut () {
      document.cookie = 'hexToken=;expires=;'
      this.$router.push('/login')
    }
  }
}
</script>
