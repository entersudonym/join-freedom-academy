<script lang="ts">
	import '../app.css';
	import Fa from '../public/fa.png';
</script>

<svelte:head>
	<title>Freedom Academy</title>
</svelte:head>

<div class="min-h-screen flex justify-center items-center bg-blue-50">
	<div class="bg-slate-50 max-w-xl rounded-lg shadow-lg shadow-blue-500/20">
		<img
			src={Fa}
			alt="A Freedom Academy-trained Spartan takes on the world"
			class="h-40 w-full object-cover rounded-t-lg"
		/>
		<slot />
	</div>
</div>
