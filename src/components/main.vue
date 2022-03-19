<template>
	<div @mouseenter="fetcher()" class="py-52 max-w-4xl mx-auto text-gray-800 text-6xl font-bold text-center transform hover:scale-150 transition duration-1000">
		<div class="uppercase">{{ text }}</div>
	</div>
</template>

<script>
	export default {
		data() {
			return { changeCheck: true, text: '..' };
		},
		methods: {
			async fetcher() {
				if (this.changeCheck) {
					this.text = 'Aman Katal';
					this.changeCheck = !this.changeCheck;
				} else {
					this.text = 'Aman Singh';
					this.changeCheck = !this.changeCheck;
				}
			},
		},
		async mounted() {
			this.text = 'Aman Singh';
		},
	};
</script>
