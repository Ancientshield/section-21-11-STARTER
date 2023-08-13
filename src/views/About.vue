<template>
	<div class="about">
		<h1>{{ $route.params.member }}</h1>
		<p>{{ store.counter }}</p>
		<p>{{ store.doubleCount }}</p>
		<button type="button" @click.prevent="store.increment">Press me!</button>
	</div>
</template>

<script>
	import { useRoute, useRouter } from 'vue-router';
	import { useCounterStore } from '../stores/counter.js';

	export default {
		setup() {
			const route = useRoute(); // this.$route 回傳的是路徑 path
			const router = useRouter(); // this.$router 回傳的是實例 object
			const store = useCounterStore();

			console.log(route.params.member);

			router.push({
				hash: '#test',
			});

			return {
				store,
			};
		},
	};
</script>
