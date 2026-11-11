<script lang="ts">
	import '../global.css'
	import favicon from '#lib/assets/favicon.svg';
	import type { LayoutProps } from './$types';
	import Navbar from './Navbar.svelte';

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<Navbar></Navbar>
{@render children()}

