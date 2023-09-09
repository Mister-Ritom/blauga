<script>
	import SideNav from '$lib/components/SideNav.svelte';
</script>

<div>
	<SideNav />
	<slot />
</div>

<style>
	div {
		display: flex;
		flex-direction: row;
		justify-content: start;
		align-items: start;
	}
</style>
