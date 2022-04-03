<template>
	<div>
		<mainc />
		<social />
		<medium />
		<contact />
	</div>
</template>

<script>
	import mainc from './components/main.vue';

	import social from './components/social.vue';

	import contact from './components/contact.vue';

	import medium from './components/medium.vue';

	export default {
		name: 'App',
		components: {
			mainc,
			social,
			contact,
			medium,
		},
	};
</script>
