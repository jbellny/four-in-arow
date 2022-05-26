<script lang='ts'>
    import { ROWS } from "./constants";
    import Token from "./Token.svelte"

    import type { Column } from "./types"

    export let column: Column

$: fullColumn = Array.from({...column, length: ROWS})
</script>

<div class="cursor-pointer flex-grow border-r border-black dark:border-white flex flex-col-reverse" on:click>
    {#each fullColumn as token, i }
        <Token {token} pos={i} />
    {/each}
</div>