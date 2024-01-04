<script>
    import WidgetCard from "../../molecules/WidgetCard/WidgetCard.svelte";

    export let data = [];
</script>

<div class="salesWidget">
    <p class="chartTitle">
        Today’s Sales
    </p>
    <div class="widgetsContainer">
        {#each data as widget}
            <WidgetCard
                    data={widget}
            />
        {/each}
    </div>
</div>

<style>
    .salesWidget{
        width: fit-content;
        height: 350px;
        padding: 30px;
        background-color: white;
        border-radius: 20px;
        position: relative;
    }

    .widgetsContainer{
        display: flex;
        height: 245px;
        position: relative;
        gap: 30px;
        align-items: center;
    }
</style>