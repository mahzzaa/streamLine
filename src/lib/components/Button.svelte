<script>
	export let size = 'medium';
	export let shadow = false;
	export let bgColor = undefined;
	export let textColor = undefined;
	export let isLeftHovered = false;
</script>

<button
on:click
	style:background-color={bgColor}
	style:color={textColor}
	class:size-lg={size === 'large'}
	class:size-md={size === 'medium'}
	class:size-sm={size === 'small'}
	class:has-left={$$slots.leftContent}
	class:shadow
>
	{#if $$slots.leftContent}
		<!-- svelte-ignore a11y-no-static-element-interactions -->
		<div class="left-content" on:mouseenter={()=> isLeftHovered = true}
			on:mouseleave={() =>  isLeftHovered =false}>
			<slot name="leftContent" />
		</div>
	{/if}
	<slot {isLeftHovered}><p>Go to home page</p></slot>
</button>

<style lang="scss">
	button {
		display: flex;
		align-items: center;
		justify-content: space-between;
		border: none;
		background-color: blue;
		color: #fff;
		padding: 15px 20px;
		font-weight: bold;
		border-radius: 5px;
		cursor: position;
		font-size: 20px;
		&:hover {
			// linear gradient in blue theme
			background: linear-gradient(45deg, #2196f3, #0e0583);
		}
		.left-content {
			padding-right: 10px;
			// max-width: 40px;
		}
		&.has-left {
			border-left: 2px solid #d9027f;
			border-right: 2px solid #d9027f;
		}
		&.size-lg {
			padding: 10px 15px;
			font-size: 30px;
		}
		&.size-md {
			padding: 15px 20px;
			font-size: 20px;
		}
		&.size-sm {
			padding: 5px 10px;
			font-size: 15px;
		}
		&.shadow {
			box-shadow: 0 0 10px rgba(14, 197, 200, 0.5);
		}
	}

	@keyframes rotation45 {
		from {
			transform: rotate(0deg);
		}

		to {
			transform: rotate(5deg);
		}
	}
</style>
