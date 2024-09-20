<script lang="ts">
	export let todos: any = [];
	let input: any;
	function handleAddTodo() {
		console.log(input.value);
	}
</script>

<div class="flex flex-col items-center justify-center w-full h-full todo-wrapper">
	<div
		class="flex flex-col items-center justify-center p-5 space-y-4 rounded-lg w-fit h-fit variant-ghost-tertiary"
	>
		<ul class="list-disc">
			<!-- //why do we need to use (todo.id) here? -->
			{#each todos as todo, index (todo.id)}
				<!-- why we use {@const} ou of <li> ? -->
				{@const number = index + 1}
				<li class="flex items-start justify-start space-x-2">
					<h2>
						{number}
					</h2>
					<p>-</p>
					<p>
						{todo.title}
					</p>
				</li>
			{/each}
		</ul>

		<!-- what is preventDefault -->
		<form
			class="flex flex-col items-center justify-center space-y-3"
			action="add-todo-form"
			on:submit|preventDefault={handleAddTodo}
		>
			<input
				placeholder="Add a new todo"
				bind:this={input}
				class="p-2 rounded-lg placeholder:text-primary-300 text-primary-700 variant-ghost-primary hover:variant-filled-primary hover:cursor-pointer focus:cursor-text"
				type="text"
			/>
			<button
				class="px-4 py-1 rounded-lg text-success-500 hover:text-primary-900 focus:text-primary-900 variant-outline-success hover:variant-filled-success"
				type="submit">Add</button
			>
		</form>
	</div>
</div>
