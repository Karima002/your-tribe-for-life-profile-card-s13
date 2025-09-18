<script>
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />

	<meta rel="author" content="Karima Mouadi">
</svelte:head>

{@render children?.()}
