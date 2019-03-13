<template>
	<div class="hello">
		<div class="left">
			<h1>{{title}}</h1>
			<!-- <h1>{{customTitle}}</h1> -->
			<ul>
				<li v-for="(link, index) in links" v-bind:key="index">
					{{link}}
				</li>
			</ul>
		</div>
		<div class="right">
			<Stats />
		</div>
	</div>
</template>

<script>
	import { mapState } from 'vuex';
	import Stats from '@/components/Stats';

	export default {
		name: 'HelloWorld',
		// computed: mapState([
		// 	'title'
		// ])
		// computed: mapState({
		// 	customTitle: 'title'
		// })
		components: {
			Stats
		},
		computed: {
			...mapState([
				'title',
				'links'
			])
		}
	}
</script>

<style>
	html,
	#app,
	.home {
		height: 100%;
	}
	body {
		background-color: #f4f4f4;
		margin: 0;
		height: 100%;
	}

	.hello {
		display: grid;
		grid-template-columns: repeat(2, 50%);
		grid-template-rows: 100%;
		grid-template-areas: "left right";
		height: 100%;
	}

	.left,
	.right {
		padding: 30px;
	}

	ul {
		list-style-type: none;
		padding: 0;
	}
	ul li {
		padding: 20px;
		background: white;
		margin-bottom: 8px;
	}

	.right {
		grid-area: right;
		background-color: #e9e9e9;
	}
</style>
