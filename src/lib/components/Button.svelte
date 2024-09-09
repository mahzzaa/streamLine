<script></script>

<button>
	<slot><p>Go to home page</p></slot>
</button>

<style lang="scss">
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

	@keyframes rotation45 {
		from {
			transform: rotate(0deg);
		}

		to {
			transform: rotate(5deg);
		}
	}
</style>
