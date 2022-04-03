<template>
	<div class="bg-gray-100">
		<div class="container mx-auto max-w-7xl px-5 py-20">
			<div class="py-5">
				<p class="uppercase m-4 text-4xl text-gray-700 text-medium">Recent Posts</p>
			</div>

			{{ posts }}

			<section class="grid grid-cols-1 md:grid-cols-3 gap-5">
				<a v-bind:href="posts[0].link" target="_blank">
					<article class="mx-auto w-full shadow-2xl transform duration-500 hover:-translate-y-2 cursor-pointer bg-white">
						<div class="min-h-80 overflow-hidden">
							<img class="h-80" v-bind:src="posts[0].thumbnail" />
						</div>
						<div class="flex justify-between">
							<p class="m-4 text-xl text-gray-700">{{ posts[0].title }}</p>
						</div>
					</article></a
				>

				<a v-bind:href="posts[1].link" target="_blank">
					<article class="mx-auto w-full shadow-2xl transform duration-500 hover:-translate-y-2 cursor-pointer bg-white">
						<div class="min-h-80 overflow-hidden">
							<img class="h-80" v-bind:src="posts[1].thumbnail" />
						</div>
						<div class="flex justify-between">
							<p class="m-4 text-xl text-gray-700">{{ posts[1].title }}</p>
						</div>
					</article></a
				>
			</section>
		</div>
	</div>
</template>

<script>
	import rssToJson from 'rss-to-json';

	export default {
		data() {
			return {
				posts: [],
			};
		},
		methods: {
			async fetchdata() {
				const url = 'https://medium.com/feed/@besoeasy';
				const data = await rssToJson.parseURL(url);
				this.posts = data.items;
			},
		},
		async mounted() {
			await this.fetchdata();
		},
	};
</script>
