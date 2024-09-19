<script>
	import TodoList from "$lib/components/TodoList.svelte";
    import {v4 as uuid} from "uuid";


    const todos=[
        {
            // why we use uuid() here? what does it do?
            id:uuid(),
            title:"Todo 1",
            completed:false
        },
        {
            id:uuid(),
            title:"Todo 2",
            completed:false
        },
        {
            id:uuid(),
            title:"Todo 3",
            completed:false
        }
    ]
</script>

<TodoList todos={todos}/>