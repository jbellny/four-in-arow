<script lang='ts'>
    import Column from "./Column.svelte";
    import { createEventDispatcher } from 'svelte'
    const dispatch = createEventDispatcher()

    const empty = () => ([],[],[],[],[],[],[])

    let board: Board = empty()
    let turn: PlayerId

</script>

<div class="w-full flex border-l border-black dark:border-white">

</div>