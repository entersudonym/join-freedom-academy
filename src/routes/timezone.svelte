<script lang="ts">
	export const prerender = true;

	import { onMount } from 'svelte';

	let timeZone;
	let showClipboardSuccess = false;
	let showDiscordNudge = false;
	onMount(() => {
		timeZone = window.Intl.DateTimeFormat().resolvedOptions().timeZone || null;
	});

	const handleClick = async (): Promise<void> => {
		if (!timeZone) {
			return;
		}

		const command = `!timezone ${timeZone}`;
		await navigator.clipboard.writeText(command);

		showClipboardSuccess = true;

		setTimeout(() => {
			showClipboardSuccess = false;

			showDiscordNudge = true;
			setTimeout(() => {
				showDiscordNudge = false;
			}, 3000);
		}, 1500);
	};
</script>

<svelte:head>
	<meta
		name="description"
		content="Set your timezone with the Freedom Academy bot with two easy steps."
	/>
</svelte:head>

<div class="py-8 px-6 text-base space-y-4 text-gray-600">
	<h1 class="text-2xl font-bold text-indigo-600">Set Your Timezone in 2 Steps</h1>

	{#if timeZone !== null}
		<ol class="space-y-2 list-inside list-decimal">
			<li>Copy the timezone command using the button below.</li>
			<li>
				Paste it directly into <a
					href={'https://discord.com/channels/540390241043873803/543115614953406474'}
					><span
						class="relative rounded p-1 cursor-pointer bg-indigo-100 hover:bg-indigo-500 hover:text-white transition-colors"
						># progress-reporting

						{#if showDiscordNudge}
							<div class="absolute w-2 h-2 -top-1 -right-1 bg-red-500 rounded-full animate-ping" />
						{/if}
					</span></a
				>
			</li>
		</ol>

		<button
			on:click={handleClick}
			class="px-6 py-2 bg-indigo-600 hover:bg-indigo-500 transition-colors rounded-lg text-white flex justify-center min-w-full"
		>
			{showClipboardSuccess ? 'Copied!' : 'Click to copy command'}
		</button>
	{:else}
		<div>Your browser isn't supported. Contact the moderators for assistance.</div>
	{/if}
</div>
