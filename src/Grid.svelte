<script lang='ts'>
    import Column from "./Column.svelte";
    import { createEventDispatcher } from 'svelte'
    import type {Board, PlayerId} from './types'
    import { PLAYERS, ROWS } from "./constants";
    import { checkWin } from "./winning";
    const dispatch = createEventDispatcher()



    const empty = () => ([[],[],[],[],[],[],[]])

    let board: Board = empty()
    let turn: PlayerId = 0

    function handleClick(index: number) {
        if (board[index].length === ROWS) {
            return
        }
        board[index].push(turn)
        board = board
        // preferred syntax for above 2 lines of code
        // board[index] = [...board[index], turn]

        if (checkWin(board, index)) {
            dispatch('win', {player: turn})
            board = empty()
        } else {
            turn = (turn + 1) % PLAYERS
        }
    }
</script>

<div class="w-full flex border-l border-black dark:border-white">
    {#each board as column, i }
        <Column {column} on:click={() => handleClick(i)}/>
    {/each}
</div>