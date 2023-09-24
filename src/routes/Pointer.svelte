<script lang="ts">
	import { spring } from 'svelte/motion';

	let coords = spring(
		{ x: -50, y: -50 },
		{
			stiffness: 0.1,
			damping: 0.25
		}
	);

	let size = spring(10);

	function handleMouseMove(e: MouseEvent) {
		coords.set({ x: e.clientX, y: e.clientY });
	}
</script>

<svelte:window
	on:mousemove={handleMouseMove}
	on:mousedown={() => size.set(30)}
	on:mouseup={() => size.set(10)}
/>

<svg>
	<circle cx={$coords.x} cy={$coords.y} r={$size} />
</svg>

<style>
	svg {
		position: fixed;
		width: 100%;
		height: 100%;
		pointer-events: none;
	}
	circle {
		fill: #55ff55;
		opacity: 0.8;
	}
</style>
