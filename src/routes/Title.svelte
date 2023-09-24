<script lang="ts">
	import harumaki from '$lib/images/harumaki.png';
	import craft from '$lib/images/craft.png';

	import { elasticOut } from 'svelte/easing';
	import { onMount } from 'svelte';
	import { tweened } from 'svelte/motion';

	const harumakiScale = tweened(0, { duration: 1000, easing: elasticOut });
	onMount(() => {
		harumakiScale.set(1);
	});
	const craftScale = tweened(0, { duration: 1000, easing: elasticOut, delay: 500 });
	onMount(() => {
		craftScale.set(1);
	});
</script>

<div class="relative h-[200px] mt-[150px]">
	<img
		class="absolute left-1/2 top-0"
		width="500"
		style="transform: translate(-50%, -50%) scale({$harumakiScale});"
		src={harumaki}
		alt="banner"
	/>
	<img
		class="absolute left-1/2 top-[90px]"
		width="300"
		style="transform: translate(-50%, -50%) scale({$craftScale});"
		src={craft}
		alt="banner"
	/>
</div>
