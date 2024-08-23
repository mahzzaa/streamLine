<script lang="ts">
	export let initialcont: number;
	export let maxCount: number;
	let message: string = '';

	let count1 = initialcont;

	function increment() {
		if (count1 === maxCount) {
			message = `Max count reached: ${maxCount}`;
			return;
		}
		count1 += 1;
		message = '';
	}
</script>

<div class="flex justify-between items-center w-full">
	<button
		class="p-3 variant-ghost-primary
"
		on:click={increment}
	>
		Click to count up 1
	</button>

	{#if message}
		<p>{message}</p>
	{:else}
		<h1>
			{count1}
		</h1>
	{/if}
</div>
