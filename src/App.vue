<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

const micmote_logo = ref(new URL('@/assets/logo.png', import.meta.url).href);
const carousel_pics = ref(
  [
    new URL('@/assets/首页1.jpg', import.meta.url).href,
    new URL('@/assets/核心技术.jpg', import.meta.url).href,
    new URL('@/assets/核心产品.jpg', import.meta.url).href,
    new URL('@/assets/核心技术.jpg', import.meta.url).href
  ]
)

</script>

<template>

  <el-container>
    <el-header class="header">
      <el-row justify="space-between" style="padding: 20px 0">
        <el-col :span="12">
          <el-image :src="micmote_logo" style="height: 18px" />
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

    <el-footer>Footer</el-footer>
  </el-container>

</template>

<style scoped>
.el-main {
  padding: 0
}
.custom-link {
  padding: 0px 5px;
  /* 上下0px，左右20px */
  text-decoration: none;
  font-size: 15px;
}

.el-header {
  height: 56px;
  background-color: #EBEEF580
}

.el-footer {
  height: 200px;
  background-color: #393a3b80
}

.demonstration {
  color: var(--el-text-color-secondary);
}

</style>
