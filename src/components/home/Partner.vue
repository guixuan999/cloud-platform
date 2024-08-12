<script setup>
import { reactive, ref } from 'vue'

const partner_pics = ref(
    [
        new URL('@/assets/uestc.png', import.meta.url).href,
        new URL('@/assets/CAICT.png', import.meta.url).href,
        new URL('@/assets/WANHUA.png', import.meta.url).href,
        new URL('@/assets/GUOTAI.png', import.meta.url).href,
    ]
)

</script>

<template>
    <div>
        <el-row style="margin: 80px 0">
            <div class="overlap">
                <p>COOPERATION | 战略合作伙伴</p>
                <p style="text-align: center; font-size: 0.5em;">众多优秀企业也选择了尘芯物联</p>
            </div>
        </el-row>
        <el-row justify="center" >
            <el-col :span="4" v-for="item of partner_pics">
                <el-image :src="item" style="width: 290px"></el-image>
            </el-col>
        </el-row>
    </div>
</template>

<style scoped>
div p {
    margin: 0
}

.overlap {
    position: absolute;
    top: 20%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: black;
    font-size: 2em;
}
</style>