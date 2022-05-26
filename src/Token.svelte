<script lang='ts'>
    import type { PlayerId } from "./types"
    import { COLORS, ROWS } from "./constants"
    import {drop} from './drop'
    export let token: PlayerId | undefined
    export let pos: number
    $: distance = (ROWS - pos) * -100
    $: color = COLORS[token]
</script>
{#if token != null}
    <div in:drop={{duration: 300, delay: 250, y: distance}} class="rounded-full h-0 pt-[100%] relative w-full bg-gradient-to-br from-[rgba(255,255,255,0.2)]" style:background-color={color}>
        <div class="inset-0 absolute rounded-full scale-[0.7] bg-gradient-to-br from-[rgba(0,0,0,0.3)]">

        </div>
    </div>
{:else}
    <div class="h-0 pt-[100%] relative w-full">
    </div>
{/if}