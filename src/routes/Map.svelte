<script lang="ts">
	import { env } from '$env/dynamic/public';
	import mapImg from '$lib/images/map.webp';
	const mapUrl = env.PUBLIC_MAP_URL;
</script>

<div class="space-y-3 text-center">
	<div class="px-4 w-full md:w-1/2 lg:w-1/3 mx-auto">
		<a href={mapUrl} target="_blank" class="hover:opacity-80">
			<img src={mapImg} alt="Jump to the map" />
		</a>
	</div>

	<div>
		<a
			href={mapUrl}
			target="_blank"
			class="text-white bg-gradient-to-br from-green-400 to-blue-600 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-green-200 dark:focus:ring-green-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center"
			>サーバーマップをみる
		</a>
	</div>
</div>
