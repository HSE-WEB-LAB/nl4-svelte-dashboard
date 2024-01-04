<script>
    import SingleBar from "../../atoms/SingleBar/SingleBar.svelte";

    export let data = [];
    export let maxValue;
</script>

<div class="chartBars">
    {#if maxValue}
        {#each data as value, index}
            <SingleBar
                    value={value.value}
                    maxValue={maxValue}
            />
        {/each}
    {/if}
</div>

<style>
    .chartBars{
        position: absolute;
        max-width: 542px;
        height: 100%;
        top: 0;
        left: 48px;
        padding: 0 0 10px 17px;
        display: flex;
        align-items: flex-end;
        gap: 17px;
        overflow: hidden;
    }
</style>