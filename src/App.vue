<template>
	<div class="container max-w-7xl mx-auto px-10">
		<mainc />
		<social />
		<medium />
	</div>
</template>

<script>
	import mainc from './components/main.vue';

	import social from './components/social.vue';

	import medium from './components/medium.vue';

	export default {
		name: 'App',
		components: {
			mainc,
			social,
			medium,
		},
	};
</script>
