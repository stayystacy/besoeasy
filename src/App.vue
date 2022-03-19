<template>
	<div class="container max-w-4xl mx-auto px-10">
		<mainc />
		<social />
		<contact />
	</div>
</template>

<script>
	import mainc from './components/main.vue';
  
	import social from './components/social.vue';

	import contact from './components/contact.vue';

	export default {
		name: 'App',
		components: {
			mainc,
			social,
			contact,
		},
	};
</script>
