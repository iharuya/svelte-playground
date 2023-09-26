<script>
	import Title from './Title.svelte';
	import ServerAddress from './ServerAddress.svelte';
	import Map from './Map.svelte';
	import McVersion from './MCVersion.svelte';
</script>

<section class="">
	<Title />
	<ServerAddress />
	<div class="flex justify-center mt-6">
		<McVersion />
	</div>
	<div class="mt-8 mb-8">
		<Map />
	</div>
</section>
