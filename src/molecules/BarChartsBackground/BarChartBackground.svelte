<script>
    export let backgroundShards;
</script>

<div class="barchartBackground">
    {#if backgroundShards}
        {#each backgroundShards as value}
            <div>
                { value }
                <span></span>
            </div>
        {/each}
    {/if}
</div>

<style>
    .barchartBackground{
        position: relative;
        width: 100%;
        height: 230px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    .barchartBackground span{
        width: 92%;
        display: block;
        height: 1px;
        background-color: #EFF1F3;
    }

    .barchartBackground div{
        width: 100%;
        position: relative;
        display: flex;
        align-items: center;
        font-size: 14px;
        color: #7B91B0;
        justify-content: space-between;
    }
</style>