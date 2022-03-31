<script context="module" lang="ts">
	export const prerender = true;
</script>

<svelte:head>
	<title>Freedom Academy</title>
</svelte:head>

<div class="min-h-screen flex justify-center items-center bg-blue-50">
	<div class="bg-slate-50 max-w-xl rounded-lg shadow-lg shadow-blue-500/20">
		<div class="bg-[url('fa.png')] h-40 bg-center bg-cover rounded-t-lg"></div>

		<div class="py-8 px-6 text-base space-y-4 text-gray-600">
			<h1 class="text-2xl font-bold text-indigo-600">The Freedom Academy</h1>
			<h4 class="text-base">
				We are a focused self-discipline and self-mastery workshop for people who
				expect success and are willing to work for it. We believe that:
			</h4>

			<ul class="space-y-2 list-inside list-disc">
				<li>Discipline is freedom</li>
				<li>Self-mastery is the key to all success in life</li>
				<li>Helping others is the secret to happiness</li>
			</ul>

			<a
				class="px-6 py-2 bg-indigo-600 hover:bg-indigo-500 transition-colors rounded-lg text-white flex justify-center min-w-full"
				href={"https://discordapp.com/invite/EqZgqEh"}
			>
				Join Us on Discord
			</a>
		</div>
	</div>
</div>
