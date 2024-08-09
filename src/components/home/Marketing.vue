<script setup>
import marketing_pic from "../../assets/mak.png"

import { reactive, ref} from 'vue'

const business = reactive(
    [
        { 
            title: "智能养殖",
            detail: "利用各种传感器技术、信息化环境监测技术、养殖环境控制技术、RFID无线电子标签识别技术、局域无线通信计划等自动控制技术，集成对生物个体识别、环境信息智能感知、数据收集与分析，达到实时监测、辅助决策的目的",
            pic: new URL('@/assets/feed_pig.png', import.meta.url).href,
            active: true
        },
        { 
            title: "工业物联网",
            detail: "将工业物联网中的终端和模组进行优化，使之变成小体积、长距离、微功耗、高性能、低成本、广应用的产品，从而大幅提高制造效率，改善产品质量，降低产品成本和资源消耗，最终实现将传统工业提升到智能化的新阶段",
            pic: new URL('@/assets/industry_iot.png', import.meta.url).href,
            active: false
        },
        { 
            title: "智慧医疗",
            detail: "秉承循证AI，赋能大健康产业的愿景，将小体积、长距离、微功耗、高性能、低成本、广应用全系统一体化的芯片运用到医疗器械中，助力医疗行业智能化升级",
            pic: new URL('@/assets/smart_medicine.png', import.meta.url).href,
            active: false
        },

    ]
)

let active_index = ref(0);

function onMouseOver(index) {
    this.active_index = index;
}

function calSpan(index) {
    if(this.active_index == index) return 5;
    return 4;
}

var calStyle = function(index) {
    if(this.active_index == index) return "background-color: #55607e";
    return '';
}

var calOpacity = function(index) {
    if(this.active_index == index) return "opacity: 1";
    return 'opacity: 0.3';
    //return "opacity: 0.5"
}
</script>

<template>
    
    <el-row class="overlapped-children">
        <el-image :src="marketing_pic"></el-image>
        <div class="overlap">
            <p>MARKETING | 业务⽅向</p>
            <p style="text-align: center; font-size: 0.5em;">高适应性，多行业通用</p>
        </div>    
    </el-row>
    <el-row justify="center" style="height: 360px; background-color: #35405e;">
        <el-col class="card overlapped-children" @mouseover="onMouseOver(index)" :span="calSpan(index)" :style="calStyle(index)" v-for="item, index of business">
            <h3 style="margin: 15px">{{ item.title }}</h3>
            <p v-if="active_index==index" style="margin: 15px">{{ item.detail }} {{ index }}</p>
            <el-image class="overlap1" :style="calOpacity(index)" :src="item.pic"></el-image>
        </el-col>
    </el-row>
</template>

<style scoped>
div p {
    margin: 0
}
.overlapped-children {
    position: relative
}

.overlap {
    position: absolute; top: 20%; left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    font-size: 2em;
}

.overlap1 {
    position: absolute; bottom: 5%; right: 5%;
}
.card {
    border: 1px solid black; color: white;
}
</style>