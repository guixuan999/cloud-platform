<script setup>
import marketing_pic from "../../assets/mak.png"
</script>

<template>
    <el-row class="overlapped-children">
        <el-image :src="marketing_pic"></el-image>
        <div class="overlap">
            <p>MARKETING | 业务⽅向</p>
            <p style="text-align: center; font-size: 0.5em;">高适应性，多行业通用</p>
        </div>
        
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
</style>