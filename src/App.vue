<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import micmote_log2 from "./assets/micmote.png"
import phone from "./assets/phone.png"
import wechat from "./assets/wechat.png"
import email from "./assets/email.png"

import router from "@/router"
// THIS ALSO WORKS
// import router from "./router/index.js"

const micmote_logo = ref(new URL('@/assets/logo.png', import.meta.url).href);

function clickme() {
  router.push('about')
}

</script>

<template>

  <el-container>
    <el-header>
      <el-row justify="space-between" style="padding: 1.25em 0">
        <el-col :span="12">
          <el-image :src="micmote_logo" style="height: 1.125em" />
        </el-col>
        <el-col :span="12">
          <RouterLink to="/" class="custom-link">首页</RouterLink>
          <RouterLink to="/about" class="custom-link">产品与技术</RouterLink>
          <RouterLink to="/table" class="custom-link">客户中心</RouterLink>
          <RouterLink to="/table" class="custom-link">尘芯新闻</RouterLink>
          <RouterLink to="/table" class="custom-link">投资者关系</RouterLink>
          <RouterLink to="/table" class="custom-link">关于尘芯</RouterLink>
          <RouterLink to="/table" class="custom-link">联系我们</RouterLink>
        </el-col>
      </el-row>
    </el-header>

    <el-main>
      <RouterView />
    </el-main>

    <el-footer style="display: flex; justify-content: center;">
      <div style="width: 60%">
        <el-row>
          <el-image :src="micmote_log2"></el-image>
        </el-row>
        <el-row>
          <el-col :span="6">
            <h1 @click="clickme" style="cursor: pointer">行业解决方案<i style="font-size: 0.8em; color: #999999"> click me</i>
            </h1>
            <p>无线电子雷管</p>
            <p>智能化养殖</p>
          </el-col>
          <el-col :span="6">
            <h1>核心产品</h1>
            <p>微功耗射频芯片</p>
            <p>微功耗计算芯片</p>
            <p>微功耗安全芯片</p>
          </el-col>
          <el-col :span="6">
            <h1>关于尘芯</h1>
            <p>公司介绍</p>
            <p>公司发展历程</p>
          </el-col>
          <el-col :span="6">
            <h1>联系我们</h1>
            <p>市场拓展：marketing@micmote.com</p>
            <p>技术支持：support@micmote.com</p>
            <p>媒体联络：PR@micmote.com</p>
          </el-col>
        </el-row>
        <el-divider />
        <el-row>
          <el-col :span="6">
            <el-link href="https://beian.miit.gov.cn/" target="_blank">蜀ICP备2023008575号-1</el-link>
          </el-col>
          <el-col :span="6" :offset="12" style="display: flex; justify-content: flex-end">
            <el-image :src="phone" />
            <el-image :src="wechat" style="padding: 0 0.625em" />
            <el-image :src="email" />
          </el-col>
        </el-row>
      </div>
    </el-footer>
  </el-container>

</template>

<style scoped>
.el-main {
  padding: 0
}

.custom-link.router-link-active {
  color: blue;
}

.custom-link {
  padding: 0px 0.3125em;
  /* 上下0px，左右20px */
  text-decoration: none;
  color: black;
}

.el-header {
  background-color: #EBEEF5F0;
  height: 3.5em;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 100;
}

.el-footer {
  height: 100%;
  width: 100%;
  background-color: black;
  color: white;
  padding: 2em 0
}

.demonstration {
  color: var(--el-text-color-secondary);
}

h1 {
  font-size: 1em;
}

p {
  font-size: 0.9em;
  color: #BBBBBB
}

.el-divider {
  margin: 0.623em 0
}
</style>
