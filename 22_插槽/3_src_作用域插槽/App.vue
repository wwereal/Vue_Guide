<template>
	<div class="container">

		<Category title="游戏">
			<template scope="mycontent"> <!--scope里的内容可以随意定-->
			<!-- mycontent是一个对象，保存slot里的自定义属性的内容 -->
				<ul>
					<li v-for="(g,index) in mycontent.games" :key="index">{{g}}</li>
				</ul>
			</template>
		</Category>

		<Category title="游戏">
			<template scope="{games,msg}">
				<!-- 解构赋值 -->
				<h3>{{msg}}</h3>
				<ol>
					<li style="color:red" v-for="(g,index) in games" :key="index">{{g}}</li>
				</ol>
			</template>
		</Category>

		<Category title="游戏">
			<template slot-scope="{games}">
				<!-- slot-scope和scope一样 -->
				<h4 v-for="(g,index) in games" :key="index">{{g}}</h4>
			</template>
		</Category>

	</div>
</template>

<script>
	import Category from './components/Category'
	export default {
		name:'App',
		components:{Category},
	}
</script>

<style scoped>
	.container,.foot{
		display: flex;
		justify-content: space-around;
	}
	h4{
		text-align: center;
	}
</style>
