<script lang="ts">
	import zanka_tired from '$lib/assets/zanka_tired.png';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={zanka_tired} />
</svelte:head>

<nav>
	<a href="/">Ty Torres</a>
	<a href="/Projects">PROJECTS</a>
</nav>


{@render children()}

