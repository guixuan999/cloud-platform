<script setup>
import { ref } from 'vue'
import imageSrc from '@/assets/leading.png'
const patent_pics = ref(
    [
        {
            url: new URL('@/assets/patent1.png', import.meta.url).href,
            text: "基于反向散射的无线总线通信方法"
        },
        {
            url: new URL('@/assets/patent2.png', import.meta.url).href,
            text: "⽆线-物联网终端的通信控制方法"
        },
        {
            url: new URL('@/assets/patent3.png', import.meta.url).href,
            text: "通过无线电直接访问总线的通信方法"
        },
        {
            url: new URL('@/assets/patent4.png', import.meta.url).href,
            text: "用于接收物联网终端信号的信号接收系统"
        },
        {
            url: new URL('@/assets/patent5.png', import.meta.url).href,
            text: "终端对收发机发送数据的解调电路"
        },
        {
            url: new URL('@/assets/patent6.png', import.meta.url).href,
            text: "物联网终端向网关发送数据的调制电路"
        },
    ]
)
</script>

<template>
    <div style="background-color: #f4f4f5; margin-top: 40px;padding-bottom: 15px;">
        <el-row justify="center">
            <el-text class="big-text">ADVANSED TECHNOLOGIES ｜专利技术</el-text>
        </el-row>
        <el-row justify="center" class="column-row" style="height: 100px; padding: 0 300px">
            <el-col :span="6">
                <div style="font-size: 6em; color: #409EFF">12<label style="font-size: 1rem; color: black">项</label>
                </div>
                <div style="font-size: 1em">发明专利</div>
            </el-col>
            <el-col :span="6">
                <div style="font-size: 6em; color: #409EFF">20<label style="font-size: 1rem; color: black">项</label>
                </div>
                <div style="font-size: 1em">软件著作</div>
            </el-col>
            <el-col :span="6">
                <div style="font-size: 6em; color: #409EFF">9<label style="font-size: 1rem; color: black">个</label>
                </div>
                <div style="font-size: 1em">硬件产品</div>
            </el-col>
        </el-row>
        <div style="background-color: #d9ecff80; margin: 50px 200px; ">
            <el-row justify="center" class="column-row" style="height: 100px;">
                <el-image style="height: 20px" :src="imageSrc" fit="cover" alt="Example Image" />
            </el-row>
            <el-row justify="center" style="height: 55%">
                <el-col :span="2" class="column-layout" v-for="{ url, text } in patent_pics" :key="url">
                    <el-image style="height: 50px" :src="url" fit="cover" alt="Example Image" />
                    <el-text style="font-size: 0.9em">{{ text }}</el-text>
                </el-col>
            </el-row>
        </div>
    </div>
</template>

<style scoped>
.column-layout {
    display: flex;
    flex-direction: column;
    /* 将子元素上下排列 */
    align-items: center;
    /* 可选：使子元素水平居中 */
    text-align: center;
    /* 可选：使文本内容居中 */

    margin: 0 60px
}

.column-row {
    display: flex;
    flex-direction: column;
    /* 将子元素垂直排列 */
    align-items: center;
    /* 可选：子元素水平居中 */
    text-align: center
}

.image {
    height: 300px
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
    padding: 0 10px
}

.overlay-button {
    position: absolute;
    bottom: 80px;
    /* 按钮距离底部的距离 */
    left: 30px;
    /* 按钮距离左侧的距离 */
    /* 其他按钮样式 */
    height: 60px;
    font-size: 22px;
}

.centered-col {
    display: flex;
    /* 启用 Flexbox 布局 */
    justify-content: center;
    /* 水平居中对齐 */
    margin: 0 10px
}
</style>