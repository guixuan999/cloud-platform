<script setup>
import { ref } from 'vue'
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
    <el-row>
        <el-col :span="24">
            <el-carousel height="1100px">
                <el-carousel-item v-for="item in carousel_pics" :key="item">
                    <el-image :src="item" />
                </el-carousel-item>
            </el-carousel>
        </el-col>
    </el-row>
</template>

<style scoped>

</style>