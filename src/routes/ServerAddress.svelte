<script lang="ts">
	import { env } from '$env/dynamic/public';
	import copyIcon from '$lib/images/copy.svg';
	import copiedIcon from '$lib/images/check.svg';
	import { fly } from 'svelte/transition';
	const serverAddress = env.PUBLIC_SERVER_ADDRESS;

	let copied = false;
	const copy = () => {
		navigator.clipboard.writeText(serverAddress);
		copied = true;
	};
</script>

<div class="text-center">
	<div
		class="inline-flex mb-2 font-semibold text-lg text-white text-center bg-gray-500/40 py-1 px-2 rounded-md"
	>
		サーバーアドレス
	</div>
	<br />
	<div class="inline-flex items-center rounded-lg bg-gradient-to-br from-green-400 to-blue-600">
		<span class="relative inline-flex items-center justify-center p-0.5 text-gray-900">
			<span id="server-address" class="relative text-2xl font-bold px-5 py-2.5 bg-white rounded-lg">
				{serverAddress}
			</span>
		</span>
		<button
			on:click={copy}
			class="relative inline-flex items-center justify-center p-0.5 text-gray-900 focus:ring-4 focus:outline-none focus:ring-green-200"
		>
			<span class="relative px-5 py-2.5 overflow-hidden">
				{#if copied}
					<img src={copiedIcon} alt="copied" width="30" in:fly={{ y: -100, duration: 1000 }} />
				{:else}
					<img src={copyIcon} alt="copy to clipboard" width="30" class="hover:opacity-60" />
				{/if}
			</span>
		</button>
	</div>
	{#if copied}
		<br />
		<div
			class="inline-flex mt-2 font-semibold text-white text-center bg-gray-500/40 py-1 px-2 rounded-md"
		>
			コピーしました
		</div>
	{/if}
</div>
