<template>
	<div class="about">
		<h1>{{ $route.params.member }}</h1>
	</div>
</template>

<script>
	import { useRoute, useRouter } from 'vue-router';

	export default {
		setup() {
			const route = useRoute(); // this.$route 回傳的是路徑 path
			const router = useRouter(); // this.$router 回傳的是實例 object

			console.log(route.params.member);

			router.push({
				hash: '#test',
			});
		},
	};
</script>
