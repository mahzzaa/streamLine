<script>
</script>

<button>
	<slot>Go back to home page</slot>
</button>

<style>
	button {
		border: none;
		background-color: blue;
		color: #fff;
		padding: 15px 20px;
		font-weight: bold;
		border-radius: 5px;
		cursor: position;
		font-size: 20px;
	}

	button:hover {
		background-color: aqua;
		color: black;
		opacity: 0.2;
		animation: rotation45 2s infinite;
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
