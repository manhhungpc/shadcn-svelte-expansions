<script lang="ts">
	import '../app.css';
	import { ModeWatcher, toggleMode } from 'mode-watcher';
	import { Button } from '$lib/components/ui/button/index.js';
	import logoSvg from '$assets/logo.svg';
</script>

<svelte:head>
	<title>Shadcn Svelte Expansion</title>
</svelte:head>

<ModeWatcher />
<div
	class="sticky top-0 mx-0 flex items-center justify-between border-b border-b-stone-500 bg-background px-6 py-3 shadow-md dark:shadow-primary-foreground"
>
	<a href="/" class="flex flex-row items-start gap-2">
		<img src={logoSvg} alt="logo" height="24" width="24" />
		<span class="text-lg font-bold">shadcn-svelte-expansions</span>
	</a>
	<div class="">
		<a href="/docs" class="mr-4 bg-stone-300 px-3 py-1 dark:bg-stone-600">Docs</a>

		<Button on:click={toggleMode} variant="outline" size="icon" class="w-max px-1">
			<p class="block dark:hidden">Light mode</p>
			<p class="hidden dark:block">Dark mode</p>
			<span class="sr-only">Toggle theme</span>
		</Button>
	</div>
</div>
<div class="mx-20 mt-8">
	<slot />
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&display=swap');
	:global(::-webkit-scrollbar) {
		width: 8px;
		background-color: #1f1f1f;
	}

	:global(::-webkit-scrollbar-thumb) {
		background-color: #444;
		border-radius: 4px;
	}
</style>
