<template>
	<div class="container max-w-4xl mx-auto px-10 py-52">
		<div @mouseenter="fetcher()" class="py-36 text-7xl font-bold text-center transform hover:scale-150 transition duration-1000">
			<div class="uppercase">{{ text }}</div>
		</div>
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
