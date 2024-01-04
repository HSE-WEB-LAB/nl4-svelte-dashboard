<script>
    import SvgView from "../../atoms/SvgView/SvgView.svelte";

    export let titleText = '';
    export let svgIcon = '';
</script>

<div class="navTitle">
    <SvgView
        svgUrl={svgIcon}
        className="navSvg"
    />
    <h1>
        { titleText }
    </h1>
</div>

<style>
    .navTitle{
        display: flex;
        align-items: center;
        gap: 30px;
        margin-bottom: 30px;
    }

    .navTitle h1{
        font-size: 30px;
        color: #000;
        font-weight: 700;
        text-align: center;
        margin: 0;
    }

    .navSvg{
        width: 56px;
        height: 56px;
    }
</style>