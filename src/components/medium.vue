<template>
	<section class="grid lg:grid-cols-3 grid-cols-1 gap-10 antialiased py-10">
		<div v-for="(collapse, index) of collapses" :key="index">
			<div class="p-1 shadow-xl bg-gradient-to-r from-pink-500 via-red-500 to-blue-500 rounded-2xl">
				<a v-bind:href="collapse.link" class="block p-6 bg-white sm:p-8 rounded-xl">
					<div class="mt-16 sm:pr-8">
						<h5 class="text-xl font-bold text-gray-900">{{ collapse.title }}</h5>

						<p class="mt-2 text-sm text-gray-500">{{ collapse.pubDate }}</p>
					</div>
				</a>
			</div>
		</div>
	</section>
</template>
<script>
	import axios from 'axios';

	export default {
		data() {
			return {
				collapses: [],
			};
		},

		methods: {
			async fetchdata() {
				try {
					const response = await axios.get('https://api.rss2json.com/v1/api.json?rss_url=https%3A%2F%2Fmedium.com%2Ffeed%2F%40besoeasy');
					this.collapses = response.data.items;
				} catch (error) {
					console.log(error);
				}
			},
		},
		async mounted() {
			await this.fetchdata();
		},
	};
</script>
