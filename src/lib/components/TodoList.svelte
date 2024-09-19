<script  lang="ts">
    export let todos : any = [];
</script>

<div class="flex flex-col justify-center">
<ul class=" list-disc ">
    <!-- //why do we need to use (todo.id) here? -->
    {#each todos as todo, index (todo.id)}
    <!-- why we use {@const} ou of <li> ? -->
        {@const number = index+1}
        <li class="flex justify-start items-start space-x-2">
            <h2>
                {number} 
            </h2>
            <p>
                - 
            </p>
            <p>
                {todo.title}
            </p>
        </li>
    {/each}
</ul>
</div>