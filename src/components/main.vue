<template>
	<div class="container max-w-4xl mx-auto px-10 py-32">
		<div @mouseenter="fetcher()" class="py-10 text-7xl font-bold text-center transform hover:scale-150 transition duration-1000">
			<div class="uppercase">AMAN SINGH KATAL</div>
			<div class="text-gray-400 text-sm text-center uppercase py-10">Mail : {{ email }}</div>
		</div>
	</div>
</template>

<script>
	const commonWords = [
		'the',
		'of',
		'and',
		'a',
		'to',
		'in',
		'is',
		'you',
		'that',
		'it',
		'he',
		'was',
		'for',
		'on',
		'are',
		'as',
		'with',
		'his',
		'they',
		'I',
		'at',
		'be',
		'this',
		'have',
		'from',
		'or',
		'one',
		'had',
		'by',
		'word',
		'but',
		'not',
		'what',
		'all',
		'were',
		'we',
		'when',
		'your',
		'can',
		'said',
		'there',
		'use',
		'an',
		'each',
		'which',
		'she',
		'do',
		'how',
		'their',
		'if',
		'will',
		'up',
		'other',
		'about',
		'out',
		'many',
		'then',
		'them',
		'these',
		'so',
		'some',
		'her',
		'would',
		'make',
		'like',
		'him',
		'into',
		'time',
		'has',
		'look',
		'two',
		'more',
		'write',
		'go',
		'see',
		'number',
		'no',
		'way',
		'could',
		'people',
		'my',
		'than',
		'first',
		'water',
		'been',
		'call',
		'who',
		'oil',
		'its',
		'now',
		'find',
		'long',
		'down',
		'day',
		'did',
		'get',
		'come',
		'made',
		'may',
		'part',
	];

	export default {
		data() {
			return { email: '' };
		},
		methods: {
			async fetcher() {
				let randomWord = commonWords[Math.floor(Math.random() * commonWords.length)];

				this.email = randomWord + '@besoeasy.com';
			},
		},
		async mounted() {
			this.email = 'a@besoeasy.com';
		},
	};
</script>
