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
          <el-image :src="micmote_logo" style="height: 30px" />
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
      <el-row>
        <el-col :span="24">
          <el-carousel height="1100px">
            <el-carousel-item v-for="item in carousel_pics" :key="item">
              <el-image :src="item" />
            </el-carousel-item>
          </el-carousel>
        </el-col>
      </el-row>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>

</template>

<style scoped>
.custom-link {
  padding: 0px 5px;
  /* 上下0px，左右20px */
  text-decoration: none;
}

.el-header {
  height: 80px;
  background-color: #EBEEF580
}

.el-footer {
  height: 200px;
  background-color: #EBEEF580
}

.demonstration {
  color: var(--el-text-color-secondary);
}

.el-carousel__item h3 {
  color: #475669;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
  text-align: center;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>
