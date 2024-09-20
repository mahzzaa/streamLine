<script>
	import { v4 as uuid } from 'uuid';

	export let todos = [];
	console.log(todos);

	let inputText = '';
	function handleAddTodo() {
		if (!inputText) return;
		// todos.push({
		// 	id: uuid(),
		// 	title: inputText,
		// 	completed: false
		// });
		// todos = todos;

		todos = [
			...todos,
			{
				id: uuid(),
				title: inputText,
				completed: false
			}
		];
		inputText = '';
	}
</script>

<div class="flex flex-col items-center justify-center w-full h-full todo-wrapper">
	<div
		class="flex flex-col items-center justify-center p-5 space-y-4 rounded-lg w-72 h-fit variant-ghost-tertiary"
	>
		<ul class="list-disc">
			<!-- ? why do we need to use (todo.id) here? -->
			{#each todos as { id, title }, index (id)}
				<!-- ? why we use {@const} ou of <li> ? -->
				{@const number = index + 1}
				<li class="flex items-start justify-start space-x-2">
					<h2>
						{number}
					</h2>
					<p>-</p>
					<p>
						{title}
					</p>
				</li>
			{/each}
		</ul>

		<div class="flex flex-col items-start justify-start w-full">
			<h1>New Todo:</h1>
			<p class="break-all">
				{inputText}
			</p>
		</div>

		<!--? what is preventDefault -->
		<form
			class="flex flex-col items-center justify-center space-y-3"
			action="add-todo-form"
			on:submit|preventDefault={handleAddTodo}
		>
			<input
				placeholder="Add a new todo"
				bind:value={inputText}
				class="p-2 rounded-lg placeholder:text-primary-300 text-primary-700 variant-ghost-primary hover:variant-filled-primary hover:cursor-pointer focus:cursor-text"
				type="text"
			/>
			<button
				disabled={!inputText}
				class="px-4 py-1 rounded-lg disabled:bg-slate-400 disabled:cursor-not-allowed text-success-500 variant-filled-success"
				type="submit">Add</button
			>
		</form>
	</div>
</div>

<style>
</style>
