<script>
    import CustomTitle from "../../atoms/CustomTitle/CustomTitle.svelte";
    import SearchLine from "../../molecules/SearchLine/SearchLine.svelte";

    let searchString = '';
</script>

<div class="topBar">
    <CustomTitle>
        DASHBOARD
    </CustomTitle>
    <SearchLine bind:modelValue={searchString}/>
</div>

<style>
    .topBar{
        position: absolute;
        top: 0;
        left: 345px;

        height: 120px;
        width: calc(100% - 345px);

        display: flex;
        padding: 0 20px;
        align-items: center;

        background-color: white;
    }
</style>