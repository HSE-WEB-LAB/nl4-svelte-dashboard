<script>

    import {onMount} from "svelte";

    export let value;
    export let maxValue;

    let targetHeight = 0;
    let currentHeight = 0;
    const maxHeight = 210;

    onMount(() => {
        targetHeight = value / maxValue * maxHeight;
        const interval = setInterval(() => {
            currentHeight += 2;
            if(currentHeight >= targetHeight) {
                clearInterval(interval);
                currentHeight = targetHeight;
            }
        }, 4);
    });
</script>


<div class="singleBarContainer">
    <div
            class="singleBar"
            style={`height: ${currentHeight}px`}
    >

    </div>
    <div class="tooltip">
        { value }
    </div>
</div>

<style>
    .singleBarContainer{
        cursor: pointer;
        position: relative;
    }

    .singleBarContainer .tooltip{
        display: none;
        position: absolute;
        left: 50%;
        transform: translateX(-50%) translateY(-100%);
        top: 0;
        color: #FA5A7D;
    }

    .singleBarContainer:hover .tooltip{
        display: block;
    }

    .singleBarContainer:hover .singleBar{
        background-color: #FA5A7D;
    }

    .singleBar{
        width: 30px;
        background-color: #5D5FEF;
        border-radius: 5px;
    }
</style>