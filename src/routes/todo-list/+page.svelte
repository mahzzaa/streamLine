<script>
	import TodoList from '$lib/components/TodoList.svelte';
	import { v4 as uuid } from 'uuid';

	let initialTodos = [
		{
			// why we use uuid() here? what does it do?
			id: uuid(),
			title: 'Todo 1',
			completed: false
		},
		{
			id: uuid(),
			title: 'Todo 2',
			completed: false
		},
		{
			id: uuid(),
			title: 'Todo 3',
			completed: false
		}
	];

	let todos = [...initialTodos];
</script>

<div class="flex flex-col items-center justify-center w-full h-full space-y-7">
	<h1>
		{todos.length} Todos
	</h1>
	<TodoList bind:todos {initialTodos} />
	<!-- <button
		on:click={() => {
			todos = [];
		}}
	>
		Restart Todos
	</button> -->
</div>
