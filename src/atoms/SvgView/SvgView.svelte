<script>
    import {onMount} from "svelte";

    export let svgUrl = '';
    export let className = '';

    let svgContainer;

    onMount(() => {
        fetch(svgUrl).then(async (data) => {
            const svg = await data.text();
            const svgDom = (new DOMParser()).parseFromString(svg, 'text/html')
            className.split(' ').forEach((classN) => {
                svgDom.body.children[0].classList.add(classN)
            })
            svgContainer.appendChild(svgDom.body.children[0])
        })
    })
</script>

<div
        bind:this={svgContainer}
        class={className}
>
</div>

<style>
    .svgContainer{
        height: fit-content;
        width: fit-content;
    }
</style>