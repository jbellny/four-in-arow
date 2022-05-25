<script lang='ts'>
    import Grid from "./Grid.svelte";
    import Scoreboard from "./Scoreboard.svelte";

    let scores = [0,0]
</script>

<Grid />
<Scoreboard {scores}/>
