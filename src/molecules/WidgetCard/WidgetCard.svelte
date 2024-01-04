<script>
    import {onMount} from "svelte";
    import SvgView from "../../atoms/SvgView/SvgView.svelte";

    export let data = {};
    let widgetOpacity = 0;

    onMount(() => {
        const interval = setInterval(() => {
            widgetOpacity += 0.01
            if(widgetOpacity >= 1) clearInterval(interval)
        }, 5)
    })
</script>

<div
        class="widgetCard"
        style={`background-color: #${data.color}; opacity: ${widgetOpacity};`}
>
    <SvgView
            svgUrl={data.icon}
            className="widgetCardIcon"
    />
    <div class="textContainer">
        <p class="widgetCardValue">
            { data.value + data.metrics }
        </p>
        <p class="valueName">
            { data.name }
        </p>
        <p class="additionalInfo">
            { data.additionalInfo }
        </p>
    </div>

</div>

<style>
    .widgetCard{
        height: 200px;
        width: 200px;
        border-radius: 16px;
        padding: 25px;
    }

    .widgetCardValue{
        margin: 10px 0 0;
        font-size: 28px;
        font-weight: 500;
    }

    .widgetCard .textContainer{
        padding-left: 5px;
    }

    .widgetCard .additionalInfo{
        color: #4079ED;
        font-size: 12px;
        font-weight: 400;
        margin-top: 3px;
    }

    .valueName{
        color: #425166;
        font-size: 16px;
        margin-top: 5px;
        font-weight: 400;
    }

    .widgetCardIcon{
        width: 45px;
        height: 45px;
    }
</style>