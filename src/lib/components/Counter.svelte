<script lang="ts">
	export let initialcont: number;
	export let maxCount: number;
	export let size: string = '3xl'; // Define size as a string type with a default value

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
	<button class={`p-3 variant-ghost-primary text-${size} text-base`} on:click={increment}>
		Click to count up 1
	</button>

	{#if message}
		<p>{message}</p>
	{:else}
		<h1>{count1}</h1>
	{/if}
</div>
