<script>
	import BiosBootScreen from '$lib/biosBootScreen/BiosBootScreen.svelte';
	import { onMount } from 'svelte';

	let loaded = false;

	onMount(() => {
		window.document.body.setAttribute('data-href', window.location.pathname);
	});
</script>

<svelte:head>
	<title>EOlsen - Desktop</title>
</svelte:head>

{#await import('$lib/Desktop.svelte') then Module}
	<Module.default bind:loaded />
{/await}
<!-- <Desktop bind:loaded /> -->
<BiosBootScreen {loaded} />
<!-- <BootScreen /> -->
