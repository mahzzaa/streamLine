<script>
	import TodoList from '$lib/components/TodoList.svelte';
	// @ts-ignore
	import { v4 as uuid } from 'uuid';

	let todos = [
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

	// @ts-ignore
	function handleAddTodo(event) {
		// event.preventDefault();
		console.log(event.detail.title);
	}
</script>

<div class="flex flex-col items-center justify-center w-full h-full space-y-7">
	<h1>
		{todos.length} Todos
	</h1>
	<TodoList {todos} on:addtodo={handleAddTodo} />
</div>
