<template>
	<div class="bg-gray-100">
		<div class="container mx-auto max-w-7xl px-5 py-20">
			<div class="py-5">
				<p class="uppercase m-4 text-4xl text-gray-700 text-medium">Recent Posts</p>
			</div>

			{{ posts }}
		</div>
	</div>
</template>

<script>
	import axios from 'axios';

	const { parse } = require('rss-to-json');

	export default {
		data() {
			return {
				posts: [],
			};
		},
		methods: {
			async fetchdata() {
				const res = await axios.get('https://medium.com/feed/@besoeasy')
				console.log(res)
				const data = await parse('https://medium.com/feed/@besoeasy');
				this.posts = data.items;
			},
		},
		async mounted() {
			await this.fetchdata();
		},
	};
</script>
