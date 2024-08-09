<script setup>
import { ref } from 'vue'
const productz_pics = ref(
    [
        new URL('@/assets/芯片级产品.jpg', import.meta.url).href,
        new URL('@/assets/模组级产品.jpg', import.meta.url).href,
        new URL('@/assets/行业解决方案.jpg', import.meta.url).href,
    ]
)
</script>

<template>
    <el-row justify="center">
        <el-text class="big-text">CORE PRODUCTS | 核心产品</el-text>
    </el-row>
    <el-row justify="center">
        <el-col :span="6" class="image-container centered-col" v-for="item in productz_pics" :key="item">

            <el-image class="image" :src="item" fit="cover" alt="Example Image" />
            <el-button class="overlay-button" type="primary" size="large">点击查看</el-button>

        </el-col>

    </el-row>
</template>

<style scoped>
.image {
    max-width: 100%; height: auto;
}

.big-text {
    font-size: 10px
}

.el-text.big-text {
    font-size: 1.5em;
    padding: 50px
}

.image-container {
    position: relative;
    display: inline-block;
    padding: 0 0
}

.overlay-button {
    position: absolute;
    bottom: 25%;
    /* 按钮距离底部的距离 */
    left: 7%;
    /* 按钮距离左侧的距离 */
    /* 其他按钮样式 */
    height: 20%;
    font-size: 15px;
}

.centered-col {
  display: flex; /* 启用 Flexbox 布局 */
  justify-content: center; /* 水平居中对齐 */
  margin: 0 10px
}

</style>