<script lang="ts">
	import '../global.css';
	import favicon from '#lib/assets/favicon.svg';
	import type { LayoutProps } from './$types';

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="app-layout">
  {@render children()}
</div>

<style>
  /* Estilos específicos do layout se necessário */
  .app-layout {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    background-color: var(--color-cloud);
    color: var(--color-ink);
  }
</style>