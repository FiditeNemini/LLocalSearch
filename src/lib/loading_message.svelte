<script lang="ts">
	import { fade } from 'svelte/transition';
	let amount = Math.floor(Math.random() * 60);
	let numbers = Array.from({ length: amount }, () => Math.floor(Math.random() * 100));

	let randomTitleLength = Math.floor(Math.random() * 10) + 3;
	let titleNumbers = Array.from({ length: randomTitleLength }, () =>
		Math.floor(Math.random() * 100)
	);
</script>

<div class="animate-pulse opacity-30" in:fade={{ duration: 200 }}>
	<div class="border border-t-neutral-300 dark:border-neutral-800 mt-10 rounded"></div>
	<div class="flex gap-1">
		{#each titleNumbers as i}
			<div class="rounded bg-neutral-400 my-2 p-2 h-6 w-10"></div>
		{/each}
	</div>

	<div
		class="rounded bg-neutral-50 dark:bg-neutral-800 border border-neutral-300 dark:border-neutral-700 max-w-prose h-fit p-2"
	>
		<div class="flex flex-row gap-1 flex-wrap">
			{#each numbers as i}
				{#if i % 3 === 0}
					<div class="rounded bg-neutral-400 p-2 h-6 w-12"></div>
				{:else if i % 5 === 0}
					<div class="rounded bg-neutral-400 p-2 h-6 w-32"></div>
				{:else if i % 7 === 0}
					<div class="rounded bg-neutral-400 p-2 h-6 w-6"></div>
				{:else if i % 9 === 0}
					<div class="rounded bg-neutral-400 p-2 h-6 w-8"></div>
				{:else}
					<div class="rounded bg-neutral-400 p-2 h-6 w-10"></div>
				{/if}
			{/each}
		</div>
	</div>
</div>
