<script setup lang="ts">
import { useRouter } from 'vue-router' //3.2setup中使用路由需要引入
const router = useRouter()//路由器提供跳转 操作
const go =()=>router.go(1)//go可以指定步数 1 -1 2 -2 等
</script>

<template>
<div class="page-header"><h2>Vue Router Demo</h2>
        <button @click="go">前进</button>&nbsp;
        <!-- 也可以直接使用方法 back forward 等-->
		<button @click="router.back">后退</button>
</div>


</template>

<style scoped>

</style>
