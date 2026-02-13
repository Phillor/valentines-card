<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
    export const ssr = false;
    export const prerender = false;
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
