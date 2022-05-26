<script lang='ts'>
    import Grid from "./Grid.svelte";
    import Scoreboard from "./Scoreboard.svelte";
    import type { WinEvent } from "./types";

    let scores = [0,0]

    function handleWin(ev: WinEvent) {
        scores[ev.detail.player] += 1
        scores = scores
    }
</script>

<Grid on:win={handleWin}/>
<Scoreboard {scores}/>
