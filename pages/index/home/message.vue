<script setup lang="ts">

// import { reactive } from 'vue'
// import { useRouter } from 'vue-router' //3.2setup中使用路由需要引入

// 定义接口约束
interface Message {
	id: string;
	title: string;
}
const state = reactive<{ messageList: Message[] }>({
	messageList: [
		{ id: '001', title: '消息001' },
		{ id: '002', title: '消息002' },
		{ id: '003', title: '消息003' },
	]
})

const router = useRouter()//路由器提供跳转 操作
// const route = useRoute() //路由提供数据使用
const pushShow = (message: Message) => {
	router.push({
		name: 'index-home-message-id-title',//多级路由用name能简化代码
		params: {
			id: message.id,
			title: message.title
		}
	}

	)
}
const pushReplace = (message: Message) => {
	router.replace({
		name: 'index-home-message-id-title',
		params: {
			id: message.id,
			title: message.title
		}
	}

	)
}

</script>

<template>
	<div>
		<ul>
			<br />
			<li v-for="message in state.messageList" :key="message.id">
				<!-- 路由传参 params 参数 方式 to的字符串写法 -->
				<!-- <router-link
					:to="`/home/message/detail/${message.id}/${message.title}`"
				>{{ message.title }}</router-link>-->

				<!-- 跳转并携带params参数，to的对象写法 -->
				<NuxtLink
					:to="{
						name: 'index-home-message-id-title',//多级路由用name能简化代码
						// path: '/home/message/detail', //使用params不能用path
						params: {
							id: message.id,
							title: message.title
						}
					}"
				>{{ message.title }} </NuxtLink> &nbsp;
				 <button @click="pushShow(message)">push查看</button>&nbsp;
				<button @click="pushReplace(message)">replace查看</button>
			</li>
		</ul>
		<hr />
		<NuxtChild />
	</div>
</template>

