<script>
	import '../app.css';
	import { env } from '$env/dynamic/public';
	const baseUrl = env.PUBLIC_BASE_URL;
	import Pointer from './Pointer.svelte';
	import landscape from '$lib/images/landscape-2.webp';
</script>

<svelte:head>
	<title>HarumakiCraft</title>
	<meta name="description" content="Minecraft server" />
	<meta property="og:description" content="はるまきのマイクラサーバー" />
	<meta property="og:title" content="HarumakiCraft" />
	<meta property="og:image" content={`${baseUrl}/ogp.png`} />
	<!-- <meta property="og:url" content={baseUrl} /> -->
</svelte:head>

<div
	id="root"
	class="min-h-screen flex flex-col relative bg-cover bg-center bg-no-repeat"
	style="background-image: url({landscape});"
>
	<main class="flex-1 flex flex-col">
		<slot />
	</main>

	<Pointer />
</div>
